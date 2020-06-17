---
description: 'Automotive Solution: Describes how to add reporting
  extensions to imports.'
title: '\[%=Heading.AnyLevel%\]'
---

Adding Reporting Extensions to Imports
======================================

It is expected that customers may want to add some additional states to
the default workflow, and some of theses states may include a process to
generate a report and/or other file type for end users to view.

For example, an Impact Report state could be added to generate a report
listing new data that would be created as a result of the import, and
existing data that would be marked for deletion. The state could be
added to the workflow screen (as described in the **Displaying Import
Modifications in Web UI** section[ here]{.mcFormatColor
style="color: Blue;"}), and a downloadable report could be made
available to the user, as shown below:

![](../../Resources/Images/QS/DownloadFile.png)

Creation of the service to generate the report requires use of the
Import Flow Extension Service (ImportFlowExtensionService), but there is
some built-in functionality to be aware of to enable users to access the
report file in the Web UI. For more information about the Import Flow
Extension Service, see the **Modifying Import Framework** topic[
here]{.mcFormatColor style="color: Blue;"}.

Files can be stored to the importflow using the **addFile** (String
attachmentID, File file) method in **ImportFlowExtensionContext**. Later
it can be accessed from another process with the **getFile** (String
attachmentID) method, using the same attachmentID with which it was
stored. For the file to display in the Report column in the Web UI, the
attachmentID has to be equal to the ID of the workflow state in which
the file should appear. See the **ImportFlowExtensionContext** interface
in the Javadoc for additional information.

However, this requires the Importflow State Report header to be
displayed in the associated workflow screen, as described in the
**Displaying the Import Details Report Column** topic within the
**Automotive Quick Start Guide** found within the **Solution
Enablement** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.
