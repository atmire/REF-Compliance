- [Date of first compliant Open Access](#DateFOA)
- [Submission](#Submission)
	- [Exception Step](#ExceptionStep)
		- [Introduction](#ExceptionStep-Introduction)
		- [Exception Step](#ExceptionStep-ExceptionStep)
		- [Type dependent Submission steps](#ExceptionStep-Type-dependent-Submission-steps)
	- [Compliance Step](#ComplianceStep)
		- [Introduction](#ComplianceStep-Introduction)
		- [Top Section](#ComplianceStep-Top)
		- [Technical and Other Exceptions](#ComplianceStep-Technical-and-Other-Exceptions)
		- [Requirements sections](#ComplianceStep-Requirements-sections)
		- [REF Compliance related data](#ComplianceStep-related-data)

# Date of first compliant Open Access <a name="DateFOA"></a> #

A curation task to update the Date of first compliant Open Access of an item is available from the list of curation tasks for items, collections and communities.

This curation task checks the embargo of an item's bitstream and updates the Date of first compliant Open Access to the end date of the embargo if the embargo has expired.

The Date of first compliant Open Access is stored in metadata field refterms.dateFOA.

# Submission <a name="Submission"></a> #

## Exception Step <a name="ExceptionStep"></a> ##

### Introduction <a name="ExceptionStep-Introduction"></a> ###

A part of the requirements as described in the [REF information and audit requirements](https://www.hefce.ac.uk/media/hefce/content/What,we,do/Research/infrastructure/Open,Access/Open%20access%20in%20the%20post-2014%20REF%20information%20and%20audit%20requirements%20udate.pdf) encompasses the open-access policy. This open access policy enables the user to fill in exceptions as to the reason why a deposit, publication,etc shouldn't be open-access.

### Exception Step <a name="ExceptionStep-ExceptionStep"></a> ###

An additional submission step has been added to give the user the possibility to enter these exceptions (**NOTE**:Only 1 exception can be given for a single item).
The "Exceptions" step occurs after the upload step and contains a couple of options, based on a configuration.

The initial page preselects the "No Exception Applicable" checkbox.

[Alt Exception Step initial](images/initial.png?raw=true "Exception Step initial")

Upon clicking a different option, extra fields are presented to the user.
These extra fields are also configurable in the same file as where the configuration for what options to show is set.

[Alt Exception Step new option clicked](images/new-option-clicked.png?raw=true "Exception Step new option clicked")

(Apart from the "No Exception applicable) There are 2 different "types" of exception-views.

1. Deposit+Access+Technical -> These Exceptions all have subdivisions. This is shown as a dropdown box containing extra options. The helptext underneath the textarea changes depending on what options was selected.
2. Other Exception -> This only contains the inputfield where the user can fill in the explanation of the exception.

[Alt Exception Step no dropdown](images/no-dropdown.png?raw=true "Exception Step no dropdown")

As stated before, only 1 exception can be present on a single item, if a new option/explanation is set, the previous is removed.
If, during the reviewstep or the workflow review, the exceptions step is show again, the page preselects and prefills the saved data.

[Alt Exception Step prefilled](images/prefilled.png?raw=true "Exception Step prefilled")

### Type dependent Submission steps <a name="ExceptionStep-Type-dependent-Submission-steps"></a> ###

Because these exceptions don't apply to all sorts of items, a type dependency system (much like the one used in the input-forms), has been added for the submission steps.
Currently, the type-dependency is set to only show the Exceptions+Compliance step for items with rioxxterms.type "Conference Paper/Proceeding/Abstract" or "Journal Article/Review".
Since an item that is initially created doesn't even contain this metadatafield, these steps aren't show.

[Alt Exception Step not dependent](images/not-dependent.png?raw=true "Exception Step not dependent")

If we then select one of the configured types, we can see that 2 more steps have appeared in the progress bar.

[Alt Exception Step type dependent](images/type-dependent.png?raw=true "Exception Step type dependent")

## Compliance Step <a name="ComplianceStep"></a> ##

### Introduction <a name="ComplianceStep-Introduction"></a> ###

The Compliance step provides an overview of the submission's compliance with hefce. If the submission is not compliant then this page will explain why and how the submission can be made compliant with HEFCE. 

### Top Section <a name="ComplianceStep-Top"></a> ###

The color of the bar at the top of the page content will immediately make it clear if the item is compliant. The bar will have a green background if the submission is compliant, or a red background when a rule has been violated. 

If there is a violation then another red bar is shown under the top bar with a summary of the actions the submitter should perform to make the submission compliant.

[Alt Compliance Step top](images/hefce-compliancestep-1.png?raw=true "Compliance Step top")

### Technical and Other Exceptions <a name="ComplianceStep-Technical-and-Other-Exceptions"></a> ###

When the submission contains a 'technical' or 'other' exception, a section "Technical and Other Exceptions" is visible. This section contains information about the exception.

[Alt Compliance Step Technical and Other Exceptions](images/hefce-compliancestep-2.png?raw=true "Compliance Step Technical and Other Exceptions")

### Requirements sections <a name="ComplianceStep-Requirements-sections"></a> ###

The Compliance page contains a separate section for each category of requirements. 

If a requirements section title is grayed out, none of the requirements in that section are applicable on the submission. If a requirement is grayed out then this requirement is not applicable on the submission.

Requirements that are not applicable to a submission are hidden by default. To show all requirements link "show all rules" under the top bar(s) can be clicked.

[Alt Compliance Step show all rules](images/hefce-compliancestep-3.png?raw=true "Compliance Step show all rules")

Requirements and requirements section titles have a question mark next to their name. When the submitter hovers over these question marks hints appear with extra information about the requirement or section. 

[Alt Compliance Step hints](images/hefce-compliancestep-4.png?raw=true "Compliance Step hints")

### REF Compliance related data <a name="ComplianceStep-related-data"></a> ###

At the bottom of the page section "REF Compliance related data" shows an overview of the submission's metadata that is relevant when determining if a submission is compliant. 

[Alt Compliance Step related data](images/hefce-compliancestep-5.png?raw=true "Compliance Step related data")
