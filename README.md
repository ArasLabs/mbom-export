# MBOM Export for Aras MPP 

This project adds an export action to the Process Plan item provided by the Aras Manufacturing Process Planning application. Resolve the Process Plan's MBOM by location and produced part, then export the result to Excel or PDF.

## History

Release | Notes
--------|--------
[v1.0.0](https://github.com/ArasLabs/mbom-export/releases/tag/v1.0.0) | First release. Tested on Aras 11 SP15 with MPP 11.0 R3 installed. 

#### Supported Aras Versions

Project | Aras
--------|------
[v1.0.0](https://github.com/ArasLabs/mbom-export/releases/tag/v1.0.0) | 11.0 SP15 w/ MPP 11.0 R3

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed
2. Aras Manufacturing Process Planning (MPP) installed
3. Aras Package Import Utility
4. aras.labs.mbom_export package

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
    * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
    * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\mbom-export\Import\imports.mf` file in the Manifest File field.
6. Select the following in the Available for Import field.
    * **aras.labs.mbom_export**
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

You are now ready to login to Aras and start exporting.

## Usage

>Note: The steps below for both use cases start from the Process Plan item window, but the Export MBOM action can also be run from the main grid. You don't have to open the Process Plan or MBOM view to use the Export MBOM action.

### Export to PDF

![Export to PDF](./Screenshots/pdf.gif)

1. From the Process Plan, select **Actions > Export MBOM** from the main menu.
2. In the Export Options dialog, select the Location and Produced Part you want to use to resolve the MBOM. 
    * These dialog fields are populated from the Locations and Produced Parts relationships on the Process Plan.
3. Select **PDF** from the Export Type dropdown list.
4. Click the **Export MBOM** button to begin the export.
5. In the new browser window that opens, enter **CRTL+P** or manually open the browser's print options.
6. Select **Microsoft Print to PDF** as the printer.
    * Note: You may need to enable the browser's background image/graphics settings in order to see the alternating table row colors.
7. Click Ok/Print.
8. When prompted by the file system, choose a location and file name for your exported PDF file.

[Click here](./Examples/PP010_MBOM_Export.pdf) to see an example of a MBOM exported to PDF.

### Export to Excel

![Export to Excel](./Screenshots/excel.gif)

1. From the Process Plan, select **Actions > Export MBOM** from the main menu.
2. In the Export Options dialog, select the Location and Produced Part you want to use to resolve the MBOM. 
    * These dialog fields are populated from the Locations and Produced Parts relationships on the Process Plan.
3. Select **Excel** from the Export Type dropdown list.
4. Click the **Export MBOM** button to begin the export.
5. In the browser prompt that appears, confirm whether you want to open or save the Excel file.
6. Open the file for viewing or editing as needed.

[Click here](./Examples/PP010_MBOM_Export.pdf) to see an example of a MBOM exported to PDF.

>Note: When you open the Excel file, you may receive a warning about the file type. This is a known issue but does not affect the usability of the file. As a workaround, run Save As on the file to avoid seeing the message next time you open workbook.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## Credits

Created by Eli Donahue for Aras Labs. @EliJDonahue

## License

Aras Labs projects are published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.)