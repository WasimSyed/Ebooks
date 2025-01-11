Overview:
With the introduction of SAPUI5, SAP has laid the foundation for modern, user-friendly enterprise software user interfaces (UIs). In this chapter, we explain how SAPUI5, SAP Fiori, and SAP Fiori elements are related; how they contribute to user-friendly interfaces; and why you should use the latter framework.

Why Do We Need New Programming Models for the Cloud?
With the increasing importance of cloud software, the trend in corporate management has been away from capital expenditures (CAPEX) to operational expenditures (OPEX):

CAPEX
These expenditures comprise all longer-term investments in a company’s assets and include one-off payments for infrastructure and software licenses. These investments must be amortized over the entire useful life of the software.

OPEX
These expenditures comprise all expenses that are necessary to enable and also continuously ensure functioning business operations. These are recurring expenses that are generally paid monthly, quarterly, or annually. They are allocated to the accounting period in which the costs were actually incurred and are recognized in full in that period.

When you contrast these two types of investments, you can understand the motivation for cloud software adoption, both on the vendor and customer side. Cloud software is typically quicker to adopt. The metrics of the commercial models are easy to understand because they are mostly based on the number of user accounts. Except for endpoints, no infrastructure investment is required. Cloud contracts usually have shorter notice periods. On the provider side, a scaling effect is also easier to achieve.

In response to this trend, SAP introduced SAP Business ByDesign as its first cloud product in 2007 after several years of development. The solution was regarded as the little brother or little sister of SAP Business Suite. The target group was small- and medium-sized enterprises. SAP was thus able to gain a great deal of valuable experience in the development and operation of cloud solutions. A few years later, the solution underwent a complete redesign to meet users’ performance expectations.

SAP Business ByDesign also used its own extension model for the first time. In the first versions, the solution didn’t yet rely on SAPUI5 as the UI technology, as it was created before the introduction of SAPUI5 and SAP Fiori. For some time now, however, SAP Business ByDesign and the associated extension concept have also relied on SAP Fiori.

Side-by-side extensions are extensions that run in parallel with the extending app on another platform. You don’t need to intervene in the actual app to develop such extensions. For cloud solutions, it’s important that SAP can provide a stable core that isn’t affected by customer extensions.

Side-by-side extensions rely on two key technological concepts: events and application programming interfaces (APIs). The app to be extended triggers events to inform potential recipients, such as the extension, that a certain event has occurred. Such events can be, for example, a change in a customer’s master data or a change in the status of an order. Based on this, the extension reads and processes the relevant data via an API. Additional entities and fields are stored in the extension.

The UIs are also provided in the extension but can be integrated into the app to be extended via the SAP Fiori launchpad. This gives users the feeling that it’s the same app. The extension is isolated by this concept and uses dedicated resources. If you decide to use the side-by-side extension model, you can use the development models for ABAP and cloud development presented in the following sections.

SAP provides SAP Business Technology Platform (SAP BTP) as the technology platform for such extensions. This platform was first introduced in 2012 under the name SAP HANA Cloud Platform and, after being renamed SAP Cloud Platform in the meantime, received its current name at the beginning of 2021. However, more than the name was new, as SAP made serious technological changes. SAP now relies even more on event-driven extensions in the cloud, as this solves many problems of customer extensions and enables stable operation of the core. True to the motto “Keep the Core clean,” side-by-side extensions with SAP BTP are now propagated as the means of choice.

However, the road to the cloud was a bit bumpy in other places. As a provider of hybrid solutions and probably also from its own painful experience, SAP has now recognized that customers can quickly become confused by the cloud or on-premise question. Making a sustainable technology decision here and now, while at the same time protecting existing investments, isn’t always easy.

Whether it was a lucky coincidence or a brilliant strategic decision by SAP that the predecessor of SAP BTP was launched at the same time as SAP HANA is something we can’t judge. Based on the initial naming SAP HANA Cloud Platform, one could assume that it was no coincidence. SAP decided on a programming model for the new in-memory platform that could be applied both in the cloud and on-premises. The apps developed on SAP HANA Extended Application Services (SAP HANA XS), that is, the application server integrated with SAP HANA, were still based on a partially proprietary JavaScript framework and Java, based on the Apache Tomcat web server. They could run both in the cloud and on-premises without a single change to the source code. With the SAP HANA XS JavaScript (XSJS) framework, the company had perhaps initially backed the wrong horse, but this decision was corrected with the introduction of SAP HANA Extended Application Services, Advanced Model. From then on, SAP relied entirely on an open framework, namely Node.js. With both Java and Node.js, which like XSJS is also based on JavaScript, SAP also addresses many developers who don’t come from the SAP cosmos. In contrast to earlier proprietary SAP technologies, these developers are now able to develop SAP extensions and independent solutions without special SAP knowledge.

With the introduction of SAP Cloud Application Programming Model in 2019, SAP also focused primarily on non-SAP developers. SAP has countered the myth that SAP technology is complicated, heavyweight, and hard to learn. In Section 4.2, we introduce aspects of SAP Cloud Application Programming Model that are relevant for SAP Fiori development.

SAP, however, still has a million-strong workforce of classic SAP developers who extend and adapt SAP products based on the ABAP programming language. Of course, SAP must not neglect this developer community in the new modern cloud world if it doesn’t want to lose them. Retraining to Java or JavaScript isn’t expedient in many cases, as it would be associated with high costs and a longer training phase. With the ABAP RESTful application programming model, SAP addresses this target group. The model can be applied to both cloud and on-premises extensions. We’ll go into the aspects of this programming model that are relevant for SAP Fiori development in Section 4.3.

You currently can’t go wrong with either SAP Cloud Application Programming Model or the ABAP RESTful application programming model. Both models are based on the Core Data Services (CDS) technology. Another common feature is that apps of both models can be operated both on SAP BTP and in an on-premises landscape without changes to the source code, which means your investments remain protected. Even if you initially start with on-premises development, you can continue to use your developments after a cloud transformation.

4.2 SAP Cloud Application Programming Model
SAP Cloud Application Programming Model focuses on the business requirements for app development. How this development is implemented, that is, the underlying technologies, is abstracted by the programming model. This also facilitates collaboration between experts from the business departments and the developers. CDS plays a key role here as a powerful language for capturing domain-specific data models.

Keeping pace with the rapidly changing world of cloud technologies and platforms is a major challenge on both the vendor side and customer side. Technologies that are current today may already be obsolete the day after tomorrow. SAP avoids a one-sided focus in SAP Cloud Application Programming Model through higher-level concepts and APIs. At the end of the day, development and architecture teams have control over which tools or technologies they choose or which architecture patterns they follow.

SAP Cloud Application Programming Model is a framework of programming and design languages, libraries, and tools for developing services and apps in the professional enterprise environment. It provides you with best practices and a variety of ready-to-use solutions for recurring tasks. SAP Cloud Application Programming Model enables you to develop full-stack apps, which refers to all components of an app from the persistence layer through business logic and service provisioning, to the UI. The framework consists of a mixture of proven as well as widely used open-source technologies and SAP technologies.

Apps with this programming model are developed either in JavaScript or in Java—both open-source frameworks. JavaScript development relies on Node.js in combination with the Express Framework. Node.js is the de facto standard for client-side JavaScript development. The Express Framework enables easy development and deployment of apps based on Node.js.

The Spring framework is used for Java development. Building on this, SAP Cloud Application Programming Model uses CDS for modeling the persistence layer and the service layer. This is a domain-specific language designed by SAP. In addition, service software development kits (SDKs) are used to access SAP S/4HANA Cloud, for example.

With SAP Cloud Application Programming Model, you can develop both locally and in the SAP BTP. If you prefer local development, you need to install Node.js and the associated Node Package Manager (npm) on your machine. Then, the apps can be deployed on SAP BTP.

Apps developed using the programming model use either SQLite or SAP HANA as the database for storing data. SQLite is a minimalist database provided as open-source software. During development, the in-memory database H2 can also be used. H2 is a relational database developed in Java. However, in this case, the data is deleted after each restart of the app. The SAP HANA database can be used both in the cloud and on-premise.

[»]  Further Planned Database Support
NoSQL and MongoDB are currently still on the road map for future supported database technologies. There is a Postgres connector for the popular open-source database Postgres that was developed by the SAP developer community.

The SAP Cloud Application Programming Model is mainly used for two scenarios:

New app development
With the programming model, you can create apps in no time at all that you can deploy in the cloud and on premise. Multitenancy, which has made SAP almost unbeatable as a provider of enterprise resource planning (ERP) solutions, is also supported by SAP Cloud Application Programming Model as standard. This gives you the ability to deploy apps to different clients independently and in complete isolation from each other.

Extension of software as a service (SaaS) apps
These SaaS apps are usually developed on an event-driven basis. An event is triggered in the SaaS app, such as changes to a customer’s data. The extension registers on this event as soon as it occurs and performs certain functions.

In SAP Cloud Application Programming Model, SAP leaves it up to the developers to decide which UI technology they want to use. However, the recommendation clearly goes in the direction of SAP Fiori elements. SAP Cloud Application Programming Model supports all annotations required for SAP Fiori elements apps.

In the following example, we’ll show you how SAP Cloud Application Programming Model is applied by means of an example. We created the sample app locally in Visual Studio Code. In our experience, this integrated development environment significantly increases the efficiency of development compared to SAP Business Application Studio.

In the first step, we initialize a new SAP Cloud Application Programming Model project using the cds init command from the command line:

cds init clouddna 
The structure of the project is specified by SAP Cloud Application Programming Model data (see Figure 4.1), and the service provision and UI are kept separate from each other.

Figure 4.1: Project Structure in SAP Cloud Application Programming Model
![image](https://github.com/user-attachments/assets/fae0d5f9-4201-4bc9-8ec8-e110181c3805)


The data model is created in the db directory, and .cds is used as the file extension. The name of the file doesn’t matter. In our example, we’ve created a file named model.cds (see Figure 4.2).

Figure 4.2: Data Model within the “db” Directory
![image](https://github.com/user-attachments/assets/8ebf9c93-6d6e-46a5-a2e0-679ac714931a)


In this file, a namespace must be declared first to avoid name conflicts with your other projects or SAP projects. In our example, we create the entities Customer and Address in the namespace at.clouddna.cap (see Listing 4.1). Both entities are extended by the aspect managed. An aspect contains certain frequently needed properties. This is an artifact provided by SAP that must be referenced via the using request.

Listing 4.1: CDS Data Model of an SAP Cloud Application Programming Model App
using { managed, sap } from '@sap/cds/common';
namespace at.clouddna.cap;
 
entity Customer: managed {
    key ID:     Integer;
    firstname:  String(50);
    lastname:   String(50);
    email:      String(100);
    phone:      String(30);
    address:    Association to Address;
}
 
entity Address: managed {
    key ID:     Integer;
    country:    String(50);
    region:     String(50);
    zip:        String(5);
    city:       String(100);
    street:     String(100);
    customer:   Association to one Customer;
} 

Via the artifact managed, the entities are enriched with the additional attributes createdAt, createdBy, modifiedAt, and modifiedBy. These fields are automatically filled at runtime and give you the possibility to determine which user created or modified an entry in the underlying database at which time.

Data types must be assigned to the individual attributes of an entity. In addition, it’s possible to map foreign key relationships. In our example, there is such a relationship (Association to) between the entities Customer and Address.

You don’t have to create the model in a single file, but you can spread it over multiple files. This makes it easier to work in teams and the models can be better structured.

After the data model has been created, the app can already be started using the following command:

cds serve 
Syntax errors may be displayed.

When starting the app, you also have the option of importing data into the database via a CSV import. To do this, you must create a file with the extension .csv in the db directory or in a subdirectory. A certain naming convention must be followed. The file name must be structured as follows: <Namespace>-<Entity>.csv (see Figure 4.3).

Figure 4.3: CSV Files for a Data Import
![image](https://github.com/user-attachments/assets/ccc308bf-6d3d-4bf7-af64-089c607bdbd9)

After creating the data model in CDS, the next step is to create the OData service. No programming experience is required for this. The service is provided in the form of files that you must create with the .cds extension in the srv directory or a subdirectory (see Figure 4.4).

Figure 4.4: OData Service in the srv Directory
![image](https://github.com/user-attachments/assets/136aee04-6032-4e85-844c-d21036c4f30b)

For our example, we created a service in the service.cds file. You can also split your service between different files. SAP Cloud Application Programming Model provides OData services of V4 in the standard. To provide the entities defined in the data model, you only need to create a projection. To do this, you must reference the previously defined data model using the using request and make it available under an alias. In the example in Listing 4.2, the alias cap was used.

Listing 4.2: Generate OData Service Using a Projection
using { at.clouddna.cap as cap } from '../db/model';
 
service UserService {
    entity Customer as projection on cap.Customer;
    entity Address as projection on cap.Address;
} 

By default, all CRUDQ methods are provided to you for each entity. These methods allow you to provide functions for creating, modifying, reading, and deleting data without programming a single line of code (see also Chapter 3, Section 3.2).

After you’ve started the app once again with the cds serve command, it’s accessible on the local host under port 4004. There, all web apps and the service endpoints of the project are provided with the associated metadata document (see Figure 4.5).

Figure 4.5: SAP Cloud Application Programming Model Application Start Page
![image](https://github.com/user-attachments/assets/25084bc3-7863-4b86-a7fb-c9afffc7a172)


Listing 4.3 shows how read-only access to the entity is allowed via an additional service.

Listing 4.3: Provisioning an Entity with Read Access
service SupportService @(path:'/support') {
    @readonly entity Customer as SELECT from cap.Customer { * } 
        excluding { createdBy, modifiedBy };
} 

On the start page of the SAP Cloud Application Programming Model app, the preview of an SAP Fiori UI (Fiori Preview app) is provided for each entity (see Figure 4.6). For this purpose, an SAP Fiori elements app is generated dynamically. This automatically generated app should only be used for testing purposes.

Figure 4.6: Fiori Preview App
![image](https://github.com/user-attachments/assets/2208dc57-f4d3-4efe-b7c7-0cd256fecada)


The appearance of the app is controlled by annotations. You can view and customize these in the service file with the extension .cds or in a separate .cds file in the srv directory. Listing 4.4 shows how the Customer entity has been annotated from the UI vocabulary. The example is limited to two annotations: SelectionFields and LineItem. You use the values of the SelectionFields annotation to control which filters are displayed. The values of the LineItem annotation control which fields are displayed in a table.

Listing 4.4: UI Annotations in the Data Model of an SAP Cloud Application Programming Model App
annotate UserService.Customer with @(
    UI: {
        SelectionFields: [ ID, firstname, lastname ],
        LineItem: [
            {   Value: ID, Label: 'Customer ID' },
            {   Value: firstname, Label: 'Firstname'},
            {   Value: lastname, Label: 'Lastname' },
            {   Value: email, Label: 'Email Address' },
            {   Value: phone, Label: 'Phone Number' }
        ]
    }
); 

Changes you make to these annotations are reflected directly in the app preview (see Figure 4.7).

Figure 4.7: SAP Fiori Elements Preview of SAP Cloud Application Programming Model App
![image](https://github.com/user-attachments/assets/b8f1ef2e-a7b8-44ff-a9d0-3fd04043603c)


In this example, we aren’t yet satisfied with the display of the Search filter names in the preview in Figure 4.7. For example, instead of the text “ID”, we would like to display the text “Customer ID (Filter)” for the first filter element. By using attribute-specific annotations, here the @title annotation, you can affect the text displayed on the UI, as shown in Listing 4.5.

Listing 4.5: Annotations for Specific Attributes
annotate UserService.Customer with {
    ID @title : 'Customer ID (Filter)';
    lastname @title : 'Lastname (Filter)';
    firstname @title : 'Firstname (Filter)';
} 

The changed annotations are then reflected in the preview in Figure 4.8.

![image](https://github.com/user-attachments/assets/a95ac234-7803-4c2b-b0d9-faa542a36b29)


The ultimate goal is to deliver the SAP Fiori UI together with SAP Cloud Application Programming Model app. SAP Cloud Application Programming Model allows the SAP Fiori app to be delivered in the app directory. For each app, a separate subdirectory must be created for this purpose. You can create the SAP Fiori apps using the Template Wizard, which is integrated into Visual Studio Code via a plug-in (see Figure 4.9). Here you can select different SAP Fiori elements floorplans for the structure of the pages, which we’ll present in detail in Part II.

![image](https://github.com/user-attachments/assets/3c5738de-5c66-44c1-9468-d4d613728bc2)

After selecting a floorplan, you must define the Data source, CAP project folder path, and the OData service (see Figure 4.10).

![image](https://github.com/user-attachments/assets/60affd6a-223a-4a1e-a40a-5afa30f22d8c)


This wizard creates a complete directory structure for your SAP Fiori elements app in the app directory (see Figure 4.11).

![image](https://github.com/user-attachments/assets/bb9f7251-8fb8-4cd5-8629-48d17746b13d)


If you now restart the SAP Cloud Application Programming Model app, the jump to the SAP Fiori elements app is offered on the start page (see Figure 4.12).

By default, this app is also included in a local SAP Fiori launchpad, which serves as the initial page. From there, you can jump to the actual app by clicking on the tile.

We’ve deliberately shown you only a small part of SAP Cloud Application Programming Model here to give you an impression of what is possible with this programming model. We were able to completely create our sample app in just a few minutes. In our view, SAP Cloud Application Programming Model is a game changer when it comes to developing modern SAP apps. You don’t need to have any prior SAP knowledge to develop SAP apps. This means that the programming model also addresses a potentially very large target group.

![image](https://github.com/user-attachments/assets/2b877dc9-d211-4773-9ac6-c676651fa509)

