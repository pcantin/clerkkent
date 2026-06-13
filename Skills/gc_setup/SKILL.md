---
name: gc_setup
description: This skill is designed for General Contractors to set up and organize construction projects effectively. It allows users to define the project scope, including tasks, materials, and labor requirements, as well as to organize project files and data in a structured manner for easy access and review. This skill serves as the foundation for managing bids, invoices, and milestones throughout the project lifecycle. It is intended to be used in conjunction with the gc_intake skill, which will be used to manage the ongoing intake of documents related to bids, invoices, and other relevant project information throughout the project lifecycle, and with the gc_manage skill, which will be used to manage milestones and analyze costs associated with the project.
---

## Features
- **Project Scope**: Define the scope of the project, including tasks, materials, and labor requirements.
- **Files Organization**: Organize project files, including plans, specifications, bids, and invoices, in a structured manner for easy access and review. 
- **Data Organization**: Organize bid and invoice data in a structured manner for easy access and review.

### Project Scope
Users can define the scope of their construction projects by outlining specific tasks, materials, and labor requirements. This feature allows for better organization and clarity when managing bids and tracking expenses.

#### General Information
To define the project scope, the user must provide the following General Information:
- **Project Name**: A unique identifier for the project.
- **Project Description**: A brief overview of the project, including its objectives and key deliverables.
- **Project Location**: The physical location where the construction project will take place. This could be, by order of preference: a specific address, a lot PID, a street, a city, or a region.
- **Project Timeline**: The expected start and end dates for the project, including any key milestones or deadlines.
- **Suppliers and Subcontractors**: A list of suppliers and subcontractors involved in the project, along with their contact information, website,and roles.
- **Other**: Any additional information relevant to the project scope that may not fit into the above categories.

#### Plans and Specifications
The skill allows users to upload and manage project plans and specifications, ensuring that all bid details are accurate and up-to-date. This helps to avoid misunderstandings and ensures that all parties involved in the bidding process have access to the necessary information.

From the provided plans and specifications, the skill can extract relevant information to populate the project scope and assist in organizing bids and invoices accordingly. 

The following information can be extracted from the plans and specifications:
- **Number of structures**: The total number of structures involved in the project.
- **Number of floors**: The total number of floors across all structures in the project.
- **Total square footage by floor**: The total square footage for each floor across all structures in the project.
- **Total square footage**: The total square footage of the entire project.
- **Estimated number of drywall sheets**: The estimated number of drywall sheets required for the project based on the total square footage and the specifications provided in the plans.
- **Foundation Type**: The type of foundation used in the project (e.g., slab, crawl space, basement).
- **Deck Type**: The type of deck used in the project (e.g., wood, composite, metal).
- **Roof Type**: The type of roof used in the project (e.g., gable, hip, flat).
- **Exterior Finish**: The type of exterior finish used in the project (e.g., brick, siding, stucco).
- **Landscaping**: The type of landscaping included in the project (e.g., grass, shrubs, trees).
- **Other**: Any additional information that can be extracted from the plans and specifications that may be relevant to the project scope.

If the user does not provide all the required **General Information** and **Plans and Specifications**, the skill will prompt them to fill in the missing details to ensure that the project scope is complete and accurate. It is possible that the user may not have all the required information at the time of project scope definition, but the skill will allow them to update the project scope as they gather more information throughout the project lifecycle.

### Data Organization
The skill provides a structured way to organize all bid and invoice data, making it easier for users to access and review information. This helps to ensure that all relevant data is readily available for analysis and decision-making throughout the project lifecycle.

The intaked data must be maintained in csv files for the different categories of information, such as bids and invoices. This allows for easy access and review of the data, as well as for integration with other tools and software that may be used for project management and cost tracking. 

Here are the csv files that will be used to organize the data:
- **ProjectScope.csv**: This file will contain all the information related to the project scope, including general information about the project, plans and specifications, and any other relevant details that define the scope of the project.
- **Suppliers.csv**: This file will contain all the information related to the suppliers and subcontractors involved in the project, including their contact information, website, and roles. This file will be used to manage relationships with suppliers and subcontractors and to ensure that all costs are accurately tracked and attributed to the correct parties.
- **Bids.csv**: This file will contain all the information related to the bids submitted by subcontractors and suppliers, including details such as supplier information, construction category, cost breakdowns, and timelines.
- **Invoices.csv**: This file will contain all the information related to the invoices received from subcontractors and suppliers, including details such as supplier information, linked bid information, cost breakdowns, and payment status.
- **Milestones.csv**: This file will contain all the information related to the milestones associated with the project, including details such as milestone name, description, associated bid and invoice information, and payment status.
- **DocumentsLog.csv**: This file will contain a log of all the documents that have been intaked into the system, including details such as document name, type, if the document is new or updated, associated supplier or subcontractor, and the date it was processed.

The data in the Bid and Invoice csv files will have enough information to enable the organization of the data in the following ways:
- By construction category (e.g., electrical, plumbing, carpentry)
- By supplier or subcontractor
- By milestone

### Files Organization
The project files will be organized the following directory structure:

#### csv files
* Data: This directory will contain all the csv data files related to the project, including the ProjectScope.csv, Suppliers.csv, Bids.csv, Invoices.csv, and Milestones.csv files. This directory will serve as the central repository for all project data, allowing for easy access and review of information throughout the project lifecycle.

### Intake Documents
* Intake: The user will put, in this directory, new original documents for intake into the system. The user will place new documents in this directory, and instruct the skill to process these documents to extract relevant information and update the corresponding csv files in the Data directory. The skill will then move the processed documents from the Intake directory to the appropriate location within the Documents directory based on the type of document and the parties involved in the project, ensuring that all relevant information is organized and easily accessible for review and analysis throughout the project lifecycle.

Most documents provided for intake will be new documents. From time to time, the user may also need to update existing documents, such as by providing updated versions of plans and specifications, or by providing additional documents related to a specific bid or invoice. In these cases, the user can place the updated documents in the Intake directory and instruct the skill to process them accordingly. The skill will then move the existing document into a subdirectory named ./old/ within the appropriate location in the Documents directory, and will then move the new document to the appropriate location in the Documents directory, ensuring that all relevant information is organized and easily accessible for review and analysis throughout the project lifecycle, while also maintaining a record of previous versions of documents for reference if needed.

The skill will also maintain the log of all documents that have been processed for intake, including details such as the document name, type, whether the document is new or updated, the associated supplier or subcontractor (if applicable), and the date it was processed. This log will be stored in the DocumentsLog.csv file within the Data directory, allowing for easy tracking and review of all documents that have been intaked into the system throughout the project lifecycle.

#### Original Documents
* Documents: This directory will contain all the original documents related to the project, including plans, specifications, bids, invoices, and any other relevant documents. This directory will be organized in a way that allows for easy access and review of all project-related documents, ensuring that all information is readily available for analysis and decision-making throughout the project lifecycle. The Documents directory will be further organized into subdirectories based on the type of document and the parties involved in the project, such as:

##### Gerneral Information files
* Documents/Plans: This subdirectory will contain all the original plan documents related to the project, allowing for easy access and review of all plans associated with the project.
* Documents/Specifications: This subdirectory will contain all the original specification documents related to the project, allowing for easy access and review of all specifications associated with the project.

##### Bids and Invoices files
* Documents/Suppliers: This directory will contain all the original documents related to the suppliers and subcontractors involved in the project, including their Bids, Invoices, and other relevant documents. Under this directory, there will be subdirectories for each supplier or subcontractor involved in the project, allowing for easy organization and access to all relevant information related to each party. Each supplier or subcontractor subdirectory will contain the following subdirectories:
* Documents/Suppliers/[supplier_name]/Bids : This subdirectory will contain all the original bid documents related to the specific supplier or subcontractor. This will allow for easy access and review of all bid documents related to each supplier or subcontractor involved in the project.
* Documents/Suppliers/[supplier_name]/Invoices : This subdirectory will contain all the original invoice documents related to the specific supplier or subcontractor. This will allow for easy access and review of all invoice documents related to each supplier or subcontractor involved in the project. The invoice subdirectory will also be further organized into two subdirectories:
* Documents/Suppliers/[supplier_name]/Invoices/Unpaid : This subdirectory will contain all the unpaid invoice original documents related to the specific supplier or subcontractor, allowing for easy access to outstanding invoices.
* Documents/Suppliers/[supplier_name]/Invoices/Paid : This subdirectory will contain all the paid invoice original documents related to the specific supplier or subcontractor, allowing for easy access to completed transactions and payment history.

##### Other files
* Documents/Other: This subdirectory will contain any other original documents related to the project that do not fit into the above categories, allowing for easy access and review of all relevant information related to the project.


#### Oganization by Construction Category
The skill allows users to categorize bids and invoices by construction category (e.g., electrical, plumbing, carpentry), making it easier to track costs and manage different aspects of the project effectively. This categorization helps users to quickly identify areas of high expenditure and potential cost-saving opportunities, as well as to allocate resources more efficiently across different construction categories.

This organization will also be used when providing the construction estimate to the bank.

Here is how the skill will organizes the data:
* Land:
  * Land Cost including HST
  * Leveling and Grading
  * Other
* Administration Fees:
  * Plans & Related Costs
  * Construction Permit
  * Site Insurance (if applicable)
  * Survey Certificate*
  * Legal Fees*
  * Other
* Land Preparation / Services:
  * Septic Tank / Well
  * Sewer / Water Hook-up
  * Excavating
  * Other
* Foundation:
  * Concrete, Footings and Forms
  * Foundation Insulation
  * Weeping Tile
  * Framing and Trusses
  * Other
* Exterior Finish:
  * Windows and Exterior Doors
  * Roofing
  * Insulation
  * Exterior Finish / Painting
  * Other
* Interior Finish:
  * Interior Doors
  * Wiring / Electrical (incl labour)
  * Plumbing / Fixtures (incl labour)
  * Flooring
  * Drywall
  * Painting
  * Cabinets -Kitchen / Other
  * Fireplace / Chimney
  * Other
* Mechanical:
  * Heating System
  * Air Conditioning / Exchange
  * Other
* Seasonal:
  * Driveway
  * Landscaping
  * Steps & Walks
  * Patio / Deck
  * Other
* Other (specify):
  * Any additional costs that do not fit into the above categories.

#### Organization by Supplier/Subcontractor
The skill enables users to organize bids and invoices by supplier or subcontractor, providing a clear overview of the contributions and costs associated with each party involved in the project. This organization helps users to manage relationships with suppliers and subcontractors more effectively and ensures that all costs are accurately tracked and attributed to the correct parties.

#### Organization by Milestone
Users can also organize bids and invoices by milestone, allowing for better tracking of payments and financial obligations throughout the project. This feature helps users to ensure that all payments are made on time and that the project stays within budget by providing a clear overview of upcoming financial commitments.

A bid line item may be linked to multiple milestones, and an invoice line item may also be linked to multiple milestones. This allows for greater flexibility in managing the financial aspects of the project and ensures that all costs are accurately tracked and attributed to the correct milestones.

## Benefits
- **Improved Accuracy**: By centralizing bid and invoice data, the skill helps reduce errors and ensures that all information is accurate and easily accessible.
- **Enhanced Decision-Making**: With detailed bid and invoice information, users can make informed decisions about which bids to accept and how to manage project costs effectively.
- **Time Savings**: Automating the bid and invoice intake process saves time and allows users to focus on other critical aspects of project management.
- **Better Collaboration**: The skill facilitates better communication and collaboration between general contractors, subcontractors, and suppliers by providing a centralized platform for managing bids and invoices. This can lead to improved relationships and more successful project outcomes.

## Use Cases
1. **Bid Management**: A general contractor can use the skill to manage multiple bids for a construction project, ensuring that all bids are organized and easily accessible for review and comparison.
2. **Cost Tracking**: The skill can be used to track all expenses related to a project, from initial bids to final invoices, providing a clear picture of the project's financial status.
3. **Budget Optimization**: By analyzing bid and invoice data, users can identify areas where costs can be reduced or optimized, helping to ensure that the project stays within budget.
4. **Project Planning**: The skill can assist in project planning by providing insights into the costs associated with different tasks and materials, allowing for better resource allocation and scheduling.


