# Viedoc Import

Command-line tool for importing clinical data into Viedoc Clinic from CSV files.

## Overview

Viedoc Import is a .NET 8 console application that transforms CSV files into ODM (Operational Data Model) XML format and imports the data into Viedoc Clinic using the Viedoc API.

## Features

- CSV to ODM XML transformation
- Configurable field mapping with expression syntax
- Support for repeating item groups with nested grouping
- Encrypted password storage using Windows DPAPI
- Batch import capabilities

## Requirements

- Windows operating system
- .NET 8.0 Runtime
- Valid Viedoc Clinic API credentials

## Installation

Download the latest release from the [Releases](../../releases) page and extract to your preferred location.

## Usage

1. Create a configuration file specifying your import settings (API URL, credentials, field mappings)
2. Prepare your CSV data file according to the expected format
3. Run the application:

```
Viedoc.Import.exe
```

The application will read the configuration, transform the CSV data, and submit it to Viedoc Clinic.

## Configuration

The application uses an XML configuration file that specifies:

- **ApiUrl** - Viedoc Clinic API endpoint
- **ClientGuid** - Your client identifier
- **UserName** / **Password** - API credentials (password can be encrypted)
- **FolderName** - Location of input CSV files
- **DefineXmlFileName** - ODM definition file
- **FileEncoding** - Character encoding for CSV files
- **FileDelimiter** - CSV delimiter character
- **AllowCreatingSubjects** - Whether to create new subjects during import
- **AllowInitiatingStudyEvents** - Whether to initiate study events during import

## Expression Syntax

Field mappings support expressions for dynamic value resolution:

- `{SubjectKey}` - Reference the subject key
- `{V1.VS.VSSBP}` - Reference a specific visit/form/item value
- `{VARNAME:format}` - Apply formatting to a value

## Support

For support and documentation, please contact Viedoc Technologies.

## License

Copyright Viedoc Technologies AB. All rights reserved.

See [LICENSE](LICENSE) for details.
