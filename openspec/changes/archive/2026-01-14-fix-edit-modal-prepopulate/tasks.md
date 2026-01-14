# Tasks

## Implementation

1. [x] Add `useEffect` to `AddAreaModal.tsx` that syncs form state when `editingArea` changes
   - When `editingArea` is provided: set `name` to `editingArea.name`, set `goal` to `editingArea.goalPomodoros.toString()`
   - When `editingArea` is null/undefined: reset to defaults (`''` and `'4'`)

2. [x] Verify existing `updateArea` function preserves `completedPomodoros`
   - The store already uses spread operator correctly: `{ ...area, ...updates }`
   - Only `name` and `goalPomodoros` are passed, so `completedPomodoros` is preserved

## Testing

3. [x] Run `npm run dev` and manually test:
   - Create area with custom name and goal
   - Complete a pomodoro to add progress
   - Edit the area - verify name and goal are pre-populated
   - Change name and/or goal, save
   - Verify progress (completed pomodoros) is preserved
   - Edit again - verify new values are shown

4. [x] Test edge cases:
   - Open add modal, then edit modal - values should differ correctly
   - Open edit for area A, close, open edit for area B - values should update

## Deployment

5. [x] Build and verify: `npm run build`
6. [x] Deploy to Vercel: `vercel --prod`
