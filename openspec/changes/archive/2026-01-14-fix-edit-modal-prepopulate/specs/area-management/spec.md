# area-management Spec Delta

## MODIFIED Requirements

### Requirement: Edit Area UI
The system SHALL provide a UI for editing existing areas.

#### Scenario: Editing an area
- **WHEN** user clicks edit button on an area card
- **THEN** a modal SHALL appear with current values pre-populated
- **AND** the name field SHALL contain the area's current name
- **AND** the goal field SHALL contain the area's current goalPomodoros value
- **AND** submitting SHALL update the area

#### Scenario: Editing preserves progress
- **WHEN** user edits an area's name or goal
- **THEN** the area's completedPomodoros SHALL be preserved
- **AND** the area's id SHALL remain unchanged

#### Scenario: Modal state resets between areas
- **WHEN** user opens edit modal for area A, closes it, then opens edit modal for area B
- **THEN** the modal SHALL show area B's values, not area A's
