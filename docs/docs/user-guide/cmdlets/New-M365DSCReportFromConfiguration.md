﻿# New-M365DSCReportFromConfiguration

## Description

This function creates a report from the specified exported configuration,
either in HTML or Excel format

## Output

This function does not generate any output.

## Parameters

| Parameter | Required | DataType | Default Value | Allowed Values | Description |
| --- | --- | --- | --- | --- | --- |
| Type | True | String |  | Excel, HTML | The type of report that should be created: Excel or HTML. |
| ConfigurationPath | True | String |  |  | The path to the exported DSC configuration that the report should be created for. |
| OutputPath | True | String |  |  | The output path of the report. |

## Examples

-------------------------- EXAMPLE 1 --------------------------

`New-M365DSCReportFromConfiguration -Type 'HTML' -ConfigurationPath 'C:\DSC\' -OutputPath 'C:\Dsc\M365Report.html'`


-------------------------- EXAMPLE 2 --------------------------

`New-M365DSCReportFromConfiguration -Type 'Excel' -ConfigurationPath 'C:\DSC\' -OutputPath 'C:\Dsc\M365Report.xlsx'`



