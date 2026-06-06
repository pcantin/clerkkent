---
name: gc_intake 
description: The GC Document Intake Skill is designed for General Contractors to manage and optimize the intake and organization of project documents. This skill allows users to upload, manage, and track documents related to construction projects, ensuring that all relevant information is easily accessible and up-to-date.
---

This skill is inteded to be used in conjunction with the gc_setup skill, which will be used to set up the initial project scope and define the suppliers and subcontractors involved in the project. The gc_document_intake skill will then be used to manage the ongoing intake of documents related to bids, invoices, and other relevant project information throughout the project lifecycle.


## Features
- **Bid Intake**: Input bids supplied by subcontractors and suppliers, including cost breakdowns and timelines.
- **Invoice Intake**: Record and manage invoices related to the project, ensuring all costs are tracked and accounted for.

### Bid Intake
Users can input bids supplied by subcontractors and suppliers, including detailed cost breakdowns and timelines. This feature helps to centralize all bid information, making it easier to review and compare different bids for the project.

When intaking a bid, the skill must be able to capture the following information:
- **Supplier Indentification**: Understand which of the suppliers listed in the project scope is submitting the bid. If this is a new supplier, the skill should prompt the user to add this supplier to the project scope.
- **Construction Category**: Identify the construction category that the bid falls under (e.g., electrical, plumbing, carpentry) to ensure that the bid is organized correctly within the project scope. It os possible that a bid may fall under multiple construction categories, in which case, if the skill is unable to identify the correct categories, the skill should then prompt the user to help clarify and specify all relevant categories for accurate organization and tracking.
- **File the original bid document**: The skill should also prompt the user to file the original bid document in the appropriate directory within the Documents folder (i.e. Documents/Suppliers/[supplier_name]/Bids), ensuring that all relevant information is readily available for review and analysis throughout the project lifecycle. The skill should also allow the user to update the bid information as needed throughout the project lifecycle to accommodate any changes or updates to the bid details, such as cost breakdowns or timelines, to ensure that all information remains accurate and up-to-date for effective project management and cost tracking.

### Invoice Intake
The skill enables users to record and manage invoices related to the project, ensuring that all costs are tracked and accounted for. This helps to maintain an accurate record of expenses and ensures that the project stays within budget.

When intaking an invoice, the skill must be able to capture the following information:
- **Supplier Identification**: Identify which supplier or subcontractor is associated with the invoice. If this is a new supplier, the skill should prompt the user to add this supplier to the project scope.
- **Link to Bid**: Normally all Invoices will be linked to a previously submitted bid. If the invoice is related to a previously submitted bid, the skill should be able to link the invoice to the corresponding bid using the unique identifier assigned to each bid line item. If the invoice is not related to a previously submitted bid, the skill should prompt the user to specify the relevant bid information, shuch as **Supplier Information** and **Construction Category**. This will ensure that the invoice is organized correctly within the project scope and that all costs are accurately tracked and attributed to the correct parties.
- **File the original invoice document**: The skill should also prompt the user to file the original invoice document in the appropriate directory within the Documents folder (i.e. Documents/Suppliers/[supplier_name]/Invoices/Paid or Documents/Suppliers/[supplier_name]/Invoices/Unpaid), ensuring that all relevant information is readily available for review and analysis throughout the project lifecycle. The skill should also allow the user to specify whether the invoice is paid or unpaid, and to update this status as needed throughout the project lifecycle to ensure that all financial obligations are accurately tracked and managed.

#### "Link to bid" feature

##### Online items identification
If the invoice lines item are not identifiable as matching any of the bid line items, it is possible that the provided indentification information is only the item code from the supplier. In this case,
the skill should use the website of the supplier to try to identify the item based on the item code, and then add a proper text name to the invoice line item based on the information found on the supplier's website. Once the item is identified, the skill should then attempt to link the invoice line item to the corresponding bid line item based on the identified item. If the skill is unable to identify the item using the supplier's website, it should prompt the user to provide additional information to help clarify and specify the correct bid line item for accurate organization and tracking.

##### Matching Invoice Line Items to Bid Line Items
Linking invoices line items to bid line items will not always be straighforward, as the invoice may include similar but not identical line items to those included in the bid, and the invoice may also include additional line items that were not included in the bid. The skill should be able to handle these scenarios by finding the best match between the invoice line items and the bid line items based on the information provided, and by prompting the user to clarify any discrepancies, duplicates, or to specify how to handle any additional line items included in the invoice.

##### Handling Cost Discrepancies
Also, if the total cost of the invoice line items exceeds the total cost of the bid line items, the skill should mark those line items as "Cost Excess".

At the end of the invoice intake process, if there are any line items marked as "Cost Excess", the skill should provide a summary of the excess costs and prompt the user to specify how to handle the excess amount, such as by allocating it to a specific construction category or by creating a new bid line item to account for the additional costs.


## Benefits
- **Improved Accuracy**: By centralizing bid and invoice data, the skill helps reduce errors and ensures that all information is accurate and easily accessible.
- **Enhanced Decision-Making**: With detailed bid and invoice information, users can make informed decisions about which bids to accept and how to manage project costs effectively.
- **Time Savings**: Automating the bid and invoice intake process saves time and allows users to focus on other critical aspects of project management.
- **Better Collaboration**: The skill facilitates better communication and collaboration between general contractors, subcontractors, and suppliers by providing a centralized platform for managing bids and invoices. This can lead to improved relationships and more successful project outcomes.


## Use Cases
1. **Bid Management**: A general contractor can use the skill to manage multiple bids for a construction project, ensuring that all bids are organized and easily accessible for review and comparison.
2. **Invoice Tracking**: The skill can be used to track all invoices related to a project, ensuring that all costs are accounted for and that the project stays within budget.
3. **Document Organization**: The skill helps to organize all project-related documents in a structured manner, making it easy for users to find and access important information when needed.
