# area-management Specification

## Purpose
TBD - created by archiving change add-area-management. Update Purpose after archive.
## Requirements
### Requirement: Add Area UI
The system SHALL provide a UI for adding new areas.

#### Scenario: Adding a new area
- **WHEN** user clicks "Add Area" button
- **THEN** a modal SHALL appear with name and goal inputs
- **AND** submitting SHALL create a new area

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

### Requirement: Delete Area UI
The system SHALL provide a UI for deleting areas.

#### Scenario: Deleting an area
- **WHEN** user clicks delete button on an area card
- **THEN** the area SHALL be removed from the list

### Requirement: Reset Progress UI
The system SHALL provide a UI for resetting all progress.

#### Scenario: Resetting progress
- **WHEN** user clicks reset progress button
- **THEN** all areas SHALL have their completedPomodoros set to 0

