# Enhanced Fixed Datatable
The Enhanced Fixed Datatable is an alternative to data tables such as DataTables. It is based on FixedDataTable, and combined with some useful features for cBioPortal team. **Now we support JSX and ES2015 by using Babel**
This infrastructure is built with generator-gulp-webapp, really appreciate the powerful JS community.

## Build Assets
To run the build with gulp, do this inside the project folder:
```
npm install
bower install
gulp
```

## Gulp commands
```gulp``` Lint files and build into dist folder  
```gulp build``` Same as above  
```gulp serve``` Start a liveload server and serve files in app folder  
```gulp serve:dist``` Start a liveload server and serve files in dist folder  
```gulp serve:test``` Run tests on browser, powered by browserSync  
```gulp wiredep``` Insert bower dependencies into index.html  


## Usage
```javascript
var testElement = <EnhancedFixedDataTable input={input} filter="NONE" download="NONE"
  showHide={false} hideFilter={true} scroller={false} fixed={[]}/>;
React.render(testElement, document.body);
```

## Configuration
**input** (required)  
  Table column info and content input.  
  type: object  
**filter**  
  Show/hide global filter or column-wise fitlers.  
  type: enum("NONE"|"ALL"|"GLOBAL"|"COLUMN_WISE") defaultValue: "NONE"  
**download**  
  Show/hide Download or Copy button.  
  type: enum("NONE"|"ALL"|"DOWNLOAD"|"COPY") defaultValue: "NONE"  
**downloadFileName**  
  Downloadable file name  
  type: string defaultValue: "data.txt"  
**showHide**  
  Show/hide the dropdown-checklist used to show/hide columns.  
  type: boolean defaultValue: false  
**hideFilter**  
  Whether to disable a filter when its related column is hidden.  
  type: boolean defaultValue: true  
**scroller**  
  Show/hide the dropdown column scroller.  
  type: boolean defaultValue: false  
**fixedChoose**  
  Show/hide the dropdown-checklist used to choose which columns will be fixed as left columns.  
  type: boolean defaultValue: true  
**uniqueId**   
  This id is part of attributes. The id name will be used to group data into rows.  
  type: string defaultValue is 'id'  
**tableWidth**  
  Fixed-datatable width  
  type: number defaultValue: 1230  
**rowHeight**  
  Fixed-datatable row height  
  type: number defaultValue: 30  
**maxHeight**  
  Fixed-datatable maximum table height  
  type: number defaultValue: 500  
**headerHeight**  
  Fixed-datatable table header height  
  type: number defaultValue: 30  
**groupHeaderHeight**  
  Fixed-datatable grouped table header height  
  type: number defaultValue: 50  
**autoColumnWidth**  
  Auto-adjust the column widht based on the value. For large dataest (More than 100,000 data points), the algorithm uses string length to calculate the width because of the performance issue. For small dataset, the algorithm uses jquery check. If in the input attributes data, attribute has column_width value, this parameter will be ignored.  
  type: boolean defaultValue: true  
**columnMaxWidth**  
  This parameter is used to specify the maximum width for each column. If the auto-calculate width bigger than this value, this value will be used instead. The library has minimum width as well. For table with header filter, the value is 130; For table without, it is 50. This value is not configurable. 130 is the minimum width for the number silder filter.  
  type: number defaultValue: 300  
**columnSorting**  
  This parameter is used to enable alphabatically showing the columns. If it sets to false, the column will be shown as the order in the input attributes.  
  type: boolean defaultValue: true  
**isResizable**  
  This parameter is used to enable isResizable in Fixed-Data-Table.
  type: boolean defaultValue: false  

## Input Data Format
The input data is an object with two attributes
* attributes: Contains column info, array of object. Each element represents a column. It has three attributes.
  * attr_id: The column ID.
  * display_name: The column display name in the table header.
  * datatype: The column type(filter type). 'STRING', 'NUMBER' and 'PERCENTAGE' are supported at this moment. You should include '%' sign for the PERCENTAGE column.  
  * column_width: Specify the column width
  * fixed: Whether Left fixed column. Default value: false  
  * show: Whether display column. Deafult value: true  
* data: Contains table content. It is the collection of objects. Each element represents a cell and it has tree attribtues:
  * attr_id: The column id of the cell
  * id(or whatever uniqueId you defined above)
  * attr_val: The cell content
  
## JSX/JS files
Babel will transfer JSX files into JS files. Any edits on JS files will not be stored back to JSX files. Please only edit JSX files if you need.
