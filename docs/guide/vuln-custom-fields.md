# Vulnerability Custom Fields

Custom fields allow you to extend vulnerability records with organization-specific information beyond the standard CVSS and description fields. This feature enables teams to track additional metadata relevant to their security processes.

## Overview

The custom fields system provides flexible data collection for vulnerabilities, allowing you to:

- Add custom text fields for additional notes
- Include dropdown selections for categorization
- Attach numerical values for scoring
- Store dates for tracking timelines
- Add checkboxes for yes/no indicators

## Creating Custom Fields

To create a new custom field:

1. Navigate to the **Admin** section
2. Click on **Custom Fields**
3. Click the **Create** button
4. Fill in the field details:
    - **Field Name**: The name for the field
    - **Label**: The display name for the field
    - **Field Type**: Select from available types (text, number, date, dropdown, checkbox)
    - **Required**: Whether the field is mandatory
    - **Default Value**: Optional default value
    - **Options**: For dropdown fields, specify available options

## Field Types

### Text Fields
- Single-line text input
- Suitable for short descriptions, IDs, or references
- Maximum length: 500 characters

### Number Fields
- Numeric input with validation
- Supports integers and decimal values
- Can be used for custom scoring systems

### Date Fields
- Date picker interface
- Useful for tracking discovery dates, remediation deadlines
- Stored in ISO format

### Dropdown Fields
- Predefined list of options
- Ensures consistent data entry
- Options are configurable per field

### Checkbox Fields
- Boolean true/false values
- Useful for flags and indicators
- Displayed as checkboxes in forms

## Using Custom Fields

Once created, custom fields appear in the vulnerability creation and editing forms:

1. Open a vulnerability record
2. Scroll to the **Custom Fields** section
3. Fill in the available custom fields
4. Save the vulnerability record

## Managing Custom Fields

### Editing Fields
- Click the **Edit** button next to any custom field
- Modify field properties as needed
- Changes apply to all future vulnerability records

### Deleting Fields
- Click the **Delete** button next to the field
- Confirm deletion in the popup dialog
- **Warning**: Deleting a field removes all associated data

### Reordering Fields
- Use the drag handles to reorder fields
- Fields appear in the same order in vulnerability forms
- Changes are saved automatically

## Best Practices

### Field Naming
- Use clear, descriptive names
- Follow your organization's naming conventions
- Avoid special characters and spaces

### Field Types
- Choose appropriate field types for your data
- Use dropdowns for standardized values
- Use text fields for free-form input

### Data Consistency
- Establish guidelines for field usage
- Train team members on field purposes
- Regularly review and clean up unused fields

## Examples

### Common Custom Field Configurations

**Business Impact**
- Type: Dropdown
- Options: Critical, High, Medium, Low
- Required: Yes

**Remediation Deadline**
- Type: Date
- Required: No
- Default: 30 days from creation

**Internal Reference**
- Type: Text
- Required: No
- Used for tracking internal ticket numbers

**Exploitability**
- Type: Checkbox
- Used to flag vulnerabilities with known exploits

**Custom Score**
- Type: Number
- Used for internal risk scoring systems