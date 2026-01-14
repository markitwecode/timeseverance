# Proposal: fix-edit-modal-prepopulate

## Summary
Fix the edit area modal to pre-populate with existing area data (name and goal pomodoros) when opened, and ensure that editing an area preserves its progress (completedPomodoros).

## Problem
Currently, when clicking the edit button on an area:
1. The modal opens with empty name and default goal of 4, regardless of the area's actual values
2. This is a React state initialization bug - `useState(editingArea?.name ?? '')` only runs once on mount, not when `editingArea` prop changes

**Root Cause:** The `AddAreaModal` component uses `useState` with initial values from `editingArea`, but React's `useState` initial value only applies on first render. When the modal reopens with a different area, the state doesn't update.

## Solution
Add a `useEffect` hook in `AddAreaModal` that syncs the form state (`name` and `goal`) whenever `editingArea` changes. This ensures:
1. When opening for edit: form is pre-populated with existing values
2. When opening for add: form is reset to defaults
3. When closing: form state doesn't leak between usages

## Impact
- **Files Changed:** 1 (`src/components/AddAreaModal.tsx`)
- **Risk:** Low - isolated to modal component
- **Backward Compatible:** Yes - no API changes

## Verification
1. Run `npm run dev`
2. Create an area "Test" with goal 6
3. Click edit on "Test"
4. Verify modal shows "Test" in name field and "6" in goal field
5. Change name to "Test2" and save
6. Verify progress (completedPomodoros) is preserved
7. Click edit again, verify "Test2" and "6" are shown
