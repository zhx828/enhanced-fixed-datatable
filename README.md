# Enhanced Fixed Datatable
The Enhanced Fixed Datatable is an alternative to data tables such as DataTables. It is based on FixedDataTable, and combined with some useful features for cBioPortal team.

## Dependencies
  -React <br />
  -jQuery <br />
  -Underscore.js <br />
  -FixedDataTable <br />
  -qTip2 <br />
  -Chosen <br />
  -React-chosen <br />
  -ZeroClipboard <br />
  -Bootstrap <br />
  -Bootstrap Dropdown-checkbox <br />
  -jQuery UI <br />
  -Font Awesome

## Usage
```javascript
var testElement = <EnhancedFixedDataTable input={input} filter="NONE" download="NONE"
  showHide={false} hideFilter={true} scroller={false} fixed={[]}/>;
React.render(testElement, document.body);
```

## Configuration
**input** (required) <br />
  Table column info and content input. <br />
  type: object <br />
**filter** <br />
  Show/hide global filter or column-wise fitlers. <br />
  type: enum("NONE"|"ALL"|"GLOBAL"|"COLUMN_WISE") defaultValue: "NONE" <br />
**download** <br />
  Show/hide Download or Copy button. <br />
  type: enum("NONE"|"ALL"|"DOWNLOAD"|"COPY") defaultValue: "NONE" <br />
**showHide** <br />
  Show/hide the dropdown-checklist used to show/hide columns. <br />
  type: boolean defaultValue: false <br />
**hideFilter** <br />
  Whether to disable a filter when its related column is hidden. <br />
  type: boolean defaultValue: true <br />
**scroller** <br />
  Show/hide the dropdown column scroller. <br />
  type: boolean defaultValue: false <br />
**fixed** <br />
  Set fixed columns.  <br />
  type: array(elements can be number or string) defaultValue is [] <br />
**uniqueId**  <br />
  This id is part of attributes. The id name will be used to group data into rows.
  type: string defaultValue is 'id'

## Input Data Format
The input data is an object with two attributes
* attributes: Contains column info, array of object. Each element represents a column. It has three attributes.
  * attr_id: The column ID.
  * display_name: The column display name in the table header.
  * datatype: The column type(filter type). 'STRING', 'NUMBER' are supported at this moment
* data: Contains table content. It is the collection of objects. Each element represents a cell and it has tree attribtues:
  * attr_id: The column id of the cell
  * id(or whatever uniqueId you defined above)
  * attr_val: The cell content
  
