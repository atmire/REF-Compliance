- [REF Open Access Compliance Checker for DSpace](#General-Introduction)
- [Submitting compliant items](#Submission)
	- [Additional Metadata](#Metadata)
	- [Registering exceptions](#ExceptionStep)
		- [Introduction](#ExceptionStep-Introduction)
		- [Exception Submission Step](#ExceptionStep-ExceptionStep)
		- [Type dependent Submission steps](#ExceptionStep-Type-dependent-Submission-steps)
	- [Assessing Compliance](#ComplianceStep)
		- [Introduction](#ComplianceStep-Introduction)
		- [Top Section](#ComplianceStep-Top)
		- [Technical and Other Exceptions](#ComplianceStep-Technical-and-Other-Exceptions)
		- [Requirements sections](#ComplianceStep-Requirements-sections)
		- [REF Compliance related data](#ComplianceStep-related-data)
- [Workflow](#Workflow)
	- [Compliance Step](#Workflow-ComplianceStep)
		- [Introduction](#Workflow-ComplianceStep-Introduction)
		- [Actions](#Workflow-ComplianceStep-Actions)
- [Accessing compliance information for live items](#Item-Compliance-View)
	- [Introduction](#Item-Compliance-View-Introduction)
	- [Navigation](#Item-Compliance-View-Navigation)
- [Curation task to set Date of first compliant Open Access (FOA)](#DateFOA)

# REF OA Compliance Checker for DSpace <a name="General-Introduction"></a> #

This documentation describes tools created to assist institutions using DSpace repositories to comply with the [audit requirements for Open access in the post-2014 Research Excellence Framework (REF)](https://www.hefce.ac.uk/media/hefce/content/What,we,do/Research/infrastructure/Open,Access/Open%20access%20in%20the%20post-2014%20REF%20information%20and%20audit%20requirements%20udate.pdf). 

Try out these features through the online demonstrator at https://hefce.atmire.com

# Submitting compliant items <a name="Submission"></a> #

## Additional metadata <a name="Metadata"></a> ##

These tools rely on the [RIOXX metadata profile and guidelines](http://rioxx.net/). In addition to the fields offered by RIOXX, following fields were added to comply with the open access requirements:
* REF target panel
* Date of first online publication, to be used in cases where an article is already available online before the official (print) publication date

The following 3 additional fields were also added. Unlike the previous fields, these are calculated automatically by DSpace and should not be manipulated manually in a production system:
* Date of first compliant deposit (FCD)
* Version of first compliant deposit (version FCD)
* Date of first compliant open access (FOA)

For testing purposes, we have made it possible on https://hefce.atmire.com to manipulate these automated fields by hand. This is why the submission on the demo server includes a step that looks like this:

![date manipulation for testing](images/date-manipulation-for-testing.png?raw=true "Date manipulation for testing")

Even though these dates are set automatically by DSpace in a production environment, someone who is testing the functionality can use this dialog to experiment by manually setting these dates and assessing the effect on the compliance of the item.

## Registering exceptions <a name="ExceptionStep"></a> ##

### Introduction <a name="ExceptionStep-Introduction"></a> ###

A part of the requirements as described in the [REF information and audit requirements](https://www.hefce.ac.uk/media/hefce/content/What,we,do/Research/infrastructure/Open,Access/Open%20access%20in%20the%20post-2014%20REF%20information%20and%20audit%20requirements%20udate.pdf) encompasses the open-access policy. The policy defines a number of exceptions to cover cases for publications that will still be eligible for the next REF, even though they don't fully comply with all openaccess requirements. A specific step has been added to the DSpace submission process, so a user can fill in exceptions as to the reason why a deposit, publication, etc does not (fully) comply with the open access requirements.

### Exception Submission Step <a name="ExceptionStep-ExceptionStep"></a> ###

An additional submission step has been added to give the user the possibility to enter these exceptions (**NOTE**:Only 1 exception can be given for a single item).
The "Exceptions" step occurs after the upload step and contains a couple of options, based on a configuration.

The initial page preselects the "No Exception Applicable" checkbox.

![Exception Step initial](images/initial.png?raw=true "Exception Step initial")

Upon clicking a different option, extra fields are presented to the user.
These extra fields are also configurable in the same file as where the configuration for what options to show is set.

![Exception Step new option clicked](images/new-option-clicked.png?raw=true "Exception Step new option clicked")

Apart from the "No Exception applicable" There are 2 different "types" of exception-views.

1. Deposit, Access and Technical Exception -> These Exceptions all have subdivisions. This is shown as a dropdown box containing extra options. The helptext underneath the textarea changes depending on what option was selected.
2. Other Exception -> This only contains the input field where the user can fill in the explanation of the exception.

![Exception Step no dropdown](images/no-dropdown.png?raw=true "Exception Step no dropdown")

As stated before, only 1 exception can be present on a single item, if a new option/explanation is set, the previous is removed.
If, during the reviewstep or the workflow review, the exceptions step is shown again, the page preselects and prefills the saved data.

![Exception Step prefilled](images/prefilled.png?raw=true "Exception Step prefilled")

### Type dependent Submission steps <a name="ExceptionStep-Type-dependent-Submission-steps"></a> ###

The DSpace submission forms have an out of the box feature to hide or show metadata fields in the describe steps, based on publication type specified at the start of the submission. This is often referred to as "type dependent submission".

However, it was not yet possible to show or hide entire submission steps, based on a publication type.

Because the REF OA exceptions only apply for conference and journal publications, a type dependency system has been put in place to hide the step to register exceptions and assess compliance for other publication types.
Currently, the type-dependency is set to only show the Exceptions and Compliance step for items with rioxxterms.type "Conference Paper/Proceeding/Abstract" or "Journal Article/Review".

The steps are hiddin up to the point when the publication type is defined.

![Exception Step not dependent](images/not-dependent.png?raw=true "Exception Step not dependent")

If we then select one of the configured types, we can see that 2 more steps have appeared in the progress bar.

![Exception Step type dependent](images/type-dependent.png?raw=true "Exception Step type dependent")

## Assessing Compliance <a name="ComplianceStep"></a> ##

### Introduction <a name="ComplianceStep-Introduction"></a> ###

The Compliance submission step provides an overview of the submission's compliance with the open access policy. If the submission is not compliant then this page will explain why and how the submission can be made compliant.

### Top Section <a name="ComplianceStep-Top"></a> ###

The color of the bar at the top of the page content will immediately make it clear if the item is compliant. The bar will have a green background if the submission is compliant, or an orange background when a rule has been violated. 

If there is a violation then another orange bar is shown under the top bar with a summary of the actions the submitter should perform to make the submission compliant.

![Compliance Step top](images/hefce-compliancestep-1.png?raw=true "Compliance Step top")

### Technical and Other Exceptions <a name="ComplianceStep-Technical-and-Other-Exceptions"></a> ###

When the submission contains a 'technical' or 'other' exception, a section "Technical and Other Exceptions" is visible. This section contains information about the exception.

![Compliance Step Technical and Other Exceptions](images/hefce-compliancestep-2.png?raw=true "Compliance Step Technical and Other Exceptions")

### Requirements sections <a name="ComplianceStep-Requirements-sections"></a> ###

The Compliance page contains a separate section for each category of requirements. 

If a requirements section title is grayed out, none of the requirements in that section are applicable on the submission. If a requirement is grayed out then this requirement is not applicable on the submission.

Requirements that are not applicable to a submission are hidden by default. To show all requirements, link "show all rules" under the top bar(s) can be clicked.

![Compliance Step show all rules](images/hefce-compliancestep-3.png?raw=true "Compliance Step show all rules")

Requirements and requirements section titles have a question mark next to their name. When the submitter hovers over these question marks hints appear with extra information about the requirement or section. 

![Compliance Step hints](images/hefce-compliancestep-4.png?raw=true "Compliance Step hints")

### REF Compliance related data <a name="ComplianceStep-related-data"></a> ###

At the bottom of the page section "REF Compliance related data" shows an overview of the submission's metadata that is relevant when determining if a submission is compliant. 

![Compliance Step related data](images/hefce-compliancestep-5.png?raw=true "Compliance Step related data")

Some of these values contain text *(estimated)*. These values were estimated so that they could be used in the compliance check. They will receive a “real” value upon item archival or at the end of the embargo. 

# Workflow <a name="Workflow"></a> #

## Compliance Step <a name="Workflow-ComplianceStep"></a> ##

### Introduction <a name="Workflow-ComplianceStep-Introduction"></a> ###

The workflow Compliance step provides an overview of the item's compliance with hefce. This step's overview contains the same information as the [submission's compliance step](#ComplianceStep).

### Actions <a name="Workflow-ComplianceStep-Actions"></a> ###

The workflow reviewer has 2 options after reviewing the compliance step:

1. Continue: Finish the compliance step and send the item to the final edit step. **Note:** This option might be disabled if the item is not compliant with the HEFCE policies. Collections can be configured to enforce item compliance before allowing the submission to continue.
2. Return: Return the item back to the edit step to resolve the issues found by the compliance step. 

![Compliance Workflow Step actions](images/hefce-actions.png?raw=true "Compliance Workflow Step actions")

# Accessing compliance information for live items <a name="Item-Compliance-View"></a> #

## Introduction <a name="Item-Compliance-View-Introduction"></a> ##

Compliance information is also available for live items in the repository, with a display that is similar to the one shown in the submission and workflow dialogs.

## Navigation <a name="Item-Compliance-View-Navigation"></a> ##

To view the item compliance view of an item the user can visit the item page and click on menu option "Item compliance" in the "Compliance" menu.

![item compliance link](images/hefce-item-compliance-link.png?raw=true "item compliance link")

**Note:** Access to compliance information for an item is only available to the original submitter, administrators and members of the group "REF Compliance Viewers". Users not in one of those groups, including anonymous users, are not able to access compliance information for archived items.

# Curation task to set Date of first compliant Open Access (FOA) <a name="DateFOA"></a> #

For items that are deposited without embargo, date of first compliant open access is set immediately when the item becomes live in the repository. For items under embargo, it is necessary to wait until the embargo actually expired and the item becomes available. The date of first compliant open access is never set to a date in the future.

A curation task to set the Date of first compliant Open Access of an item is available from the list of curation tasks for items, collections and communities.

This curation task checks the embargo of an item's bitstream and updates the Date of first compliant Open Access to the end date of the embargo if the embargo has expired.

The Date of first compliant Open Access is stored in metadata field refterms.dateFOA. This date is considered to be immutable: it should not be manipulated manually by an administrator once it is set.
