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

4.3 ABAP RESTful Application Programming Model
From SAP’s perspective, it makes sense to enable cloud development for ABAP developers as well. In this way, the new technology can be combined with the experience of the large ABAP developer community. Existing know-how can also continue to be applied in the cloud. SAP has developed the ABAP RESTful application programming model for this purpose. Apps developed with this programming model can be executed both in SAP BTP and on-premise SAP S/4HANA systems. Like SAP Cloud Application Programming Model, SAP has killed two birds with one stone.

The ABAP RESTful application programming model has little to do with classic ABAP development. Rather, it’s a modern programming model based entirely on CDS and SAP Fiori. In the evolution of ABAP programming models, the ABAP RESTful application programming model currently represents the final stage. The classic ABAP programming model, which had proven itself over decades, was initially replaced in 2012 by the ABAP programming model for SAP Fiori. Its successor, in turn, is the ABAP RESTful application programming model. Because this programming model can only be executed in the cloud and on SAP S/4HANA, the predecessor models for older releases remain valid.

The ABAP RESTful application programming model has unified the development of ABAP apps based on OData services. It’s based on three pillars that make development easier for you:

Tools
The ABAP Development Tools (ADT) integrated in the Eclipse development environment can be used to perform all implementation tasks. This allows you to optimize the workflow in development projects. Newly introduced development artifacts help you standardize development. These artifacts include, for example, CDS views, metadata extensions, and ABAP-managed database procedures (AMDP).

Language
The ABAP programming language was adapted, modernized, and extended for the ABAP RESTful application programming model. The goal here was to support CDS and enable SAP cloud app extensions without compromising the stability of the app core. Commands that aren’t useful in the cloud context can therefore no longer be used with the ABAP RESTful application programming model. You use typed APIs for standard implementation tasks and benefit from features such as auto-completion, static code checks, and element information.

Frameworks
Powerful and modern frameworks form the third important pillar of the programming model. These frameworks, which include SAP Gateway and the Orchestration Framework (OF), support you in standard implementation tasks.

Figure 4.13 illustrates the architecture of the ABAP RESTful application programming model. The lowest level is the data modeling based on business objects. The intermediate layer is service provisioning in the form of OData services. At the service consumption level, SAP Fiori element apps or API-based web apps can be used. In the following, we’ll go into more detail about the individual components of this architecture.

Figure 4.13: Architecture of the ABAP RESTful Application Programming Model
![image](https://github.com/user-attachments/assets/549791e2-0ac0-417e-85d3-55d955254396)


A business object is a common artifact in enterprise app development. It represents an object in the enterprise world, for example, an order, a product, or a business partner. Structurally, a business object consists of a hierarchical tree made up of multiple nodes. For example, a purchase order contains several purchase order items, which in turn are made up of several products. The nodes of this structure are connected by a special type of association called a composition. Each node of this composition tree is modeled as a CDS entity. The root entity represents the business object to the outside world. It represents the top node within the hierarchy.

A behavior can be defined for each business object. This defines the operations and field properties of a single business object. A behavior definition thus contains behavior characteristics and a set of operations for each entity along the composition tree of a business object. The behavior is modeled using the Behavior Definition Language (BDL).

The business object is basically service independent, which means it’s created independently of any OData service layer. The business object therefore comprises the maximum range of functions that can be used by a specific OData service that provides, that is, projects, this business object.

The projection layer is the first service-specific layer created during the development project. With the projection of the business object, you define the real behavior of a business object in an OData service. This intermediate layer gives you a lot of flexibility in how you want to use the business object in different OData services. For example, the underlying business object can be extended without affecting existing OData services.

The projection is created using a CDS view. Usually, interface and consumption views are used for this purpose. An interface view looks like a direct projection at an underlying database table. It doesn’t include annotations from the UI vocabulary. Listing 4.6 shows an example of an interface view from one of our demo apps.

Listing 4.6: CDS Projection with an Interface View
@AbapCatalog.sqlViewName: 'ZMOXIS_DEMO_CDSS'
@AbapCatalog.compiler.compareFilter: true
@AbapCatalog.preserveKey: true
@AccessControl.authorizationCheck: #CHECK
@EndUserText.label: 'Moxis Demo'
@Metadata.allowExtensions: true
define view ZI_MOXIS_DEMO_CDS as select from /moxis/doc {
    key guid as Guid,t,
    order_text as OrderText,
    moxis_job_descr as MoxisJobDescr,
    moxis_order_id as MoxisOrderId,
    created_by as CreatedBy,
    created_date as CreatedDate,
    moxis_job_status as MoxisJobStatus,
    document_name as DocumentName
} 

A consumption view is based on several interface views. It contains annotations from the UI vocabulary and is intended for use in a specific SAP Fiori app. Listing 4.7 shows an example of a consumption view.

Listing 4.7: Consumption View with Various UI Annotations
@AbapCatalog.sqlViewName: 'ZC_MOXIS_DEMO'
@AbapCatalog.compiler.compareFilter: true
@AbapCatalog.preserveKey: true
@AccessControl.authorizationCheck: #CHECK
@EndUserText.label: 'Moxis Demo Consumption View'
define view ZC_MOXIS_DEMO_CDS as select from ZI_MOXIS_DEMO_CDS {
    
    @UI.hidden: true
    key Guid,
 
    @UI.lineItem: [{position:10, importance: #HIGH,
                    label: 'Job Description}]'
    OrderText,
    
    @UI.selectionField: [{position:20}]
    @UI.lineItem: [{position:20, importance: #MEDIUM,
                    label: 'Moxis Status'}]
    MoxisJobStatus,
    
    @UI.selectionField: [{position:40}]
    @UI.lineItem: [{position:20, importance: #MEDIUM,
                    label: 'Created at'}]
    CreatedDate,
    
    @UI.selectionField: [{position:30}]
    @UI.lineItem: [{position:30, importance: #HIGH,
                    label: 'Created by'}]
    CreatedBy
} 

The service binding is another ABAP repository object used to bind the service definition to a client-server communication protocol. In the SAP context, the communication protocol is usually OData. Like any other ABAP repository object, the service binding uses the proven infrastructure of the ABAP Workbench, including the transport functionality. The service binding is created using the ADT. In the form of the binding type, you specify which OData version and consumption type should be used to provide a service (see Figure 4.14). Currently OData V2 and V4 are supported.

Figure 4.14: Create Service Binding in ABAP Development Tools
![image](https://github.com/user-attachments/assets/cd92212a-72bf-4e95-8b59-cc770400fc70)


The OData services are provided either as UI services for consumption in SAP Fiori apps or as web APIs for consumption in any OData client. Any frontend configuration performed in the form of annotations from the UI vocabulary in the backend is included in the OData service metadata.

An SAP Fiori elements app reads the metadata information, interprets it, and derives the appropriate UIs from it. The metadata of an OData service provided as a web API doesn’t contain any UI-specific information.

To test the annotations, you’ve defined in the consumption view, you can start a preview in the default browser of your operating system when you create the service binding in the ADT. To do this, click the Preview button. You can see the preview for the example presented in this section in Figure 4.15.

Figure 4.15: Preview the UI of the SAP Fiori Elements App in the ABAP Development Tools
![image](https://github.com/user-attachments/assets/db76a974-498c-40fd-bdcd-c6f267395008)


As you can see, there are many parallels between SAP Cloud Application Programming Model and the ABAP RESTful application programming model. This makes it very easy for developers to switch from one model to the other or to work with both models. In this chapter, we’ve only provided an overview of how the two programming models work because the focus of this book is on consuming services in SAP Fiori elements. For development with SAP Cloud Application Programming Model, you should be familiar with JavaScript or Java, and for development with the ABAP RESTful application programming model, you should be familiar with ABAP if you want to implement more complex requirements.


Chapter 6: Introduction to Floorplans and Application Scenarios
Overview
In the development of business apps, there are always use cases that require the representation of data in similar formats. Whether lists, tables, forms, or graphics, SAP Fiori elements provides suitable floorplans are available for all.

From the most diverse requirements for business apps, comparable use cases crystallize again and again in which data must be presented in a certain way. To implement these use cases as simply as possible and with relatively little development effort, you can fall back on floorplans. Admittedly, you’re more flexible if you develop your own freestyle SAPUI5 apps. However, freestyle development is more complex and requires in-depth knowledge of SAPUI5 development. If you rely on SAP Fiori elements instead, you can create apps with little knowledge of SAPUI5. At the same time, you automatically achieve a consistent user interface (UI) design, and your apps comply with the SAP Fiori design guidelines.

In this chapter, we give you an overview of the floorplans available with SAP Fiori elements and their app scenarios. To this end, we’ll first discuss the individual floorplans in Section 6.1. Then, in Section 6.2, we’ll introduce you to their use cases. Finally, in Section 6.3, you’ll learn about some annotations that can be used generically for all floorplans.

6.1 Available Floorplans
SAP Fiori elements offers you a range of floorplans. Whether you want to create an overview page with key figures or simply display a large amount of data in list form, there is a floorplan for every common use case. In addition to a list display, you can also create a detailed view for the individual objects within this list, which you can jump to when you select an object. You can use this detailed view to create new objects or edit existing ones. And statistical data can also be displayed in various ways with a floorplan.

We briefly introduce the available floorplans and their functions in the following sections. We’ll then show a detailed development example for each floorplan type.

[»]  OData Version
The individual floorplans sometimes differ depending on which OData version you’re using. Versions 2 and 4 are available, so it could be that certain functions or annotations are only available in one of the two versions or work differently in the two versions. In the following examples we use OData V2.

6.1.1 Overview Page
If you want to display an overview or dashboard for a specific business area or topic, it’s best to use the floorplan overview page for this purpose. The overview page is particularly suitable for displaying the following information:

Key tasks to be completed

Various notes on a task area

Various key performance indicators (KPIs)

In addition, you can also display diagrams and graphics on an overview page. The data displayed on the overview page is usually compiled from a variety of sources and is intended to provide the user with an overall view. For example, you could show data on all your products, customers, suppliers, or similar on an overview page.

Figure 6.1 shows what an overview page might look like. Cards are used to display the data. Cards are design elements on which the most important information about an object can be clearly displayed. Similar to tiles, cards allow a UI that brings together information on several objects or from several apps to be structured dynamically and clearly. This floorplan is also characterized by this design element. What kind of content you place on the individual cards is up to you. You can display tables, lists, diagrams, or tiles of any kind within the individual cards.

Basically, an overview page consists of two areas:

Dynamic page header

Dynamic page content

In the upper area of the app is the dynamic page header (Figure 6.1 ➊), which contains general information about the app. Here, for instance, the title describes the area for which the app provides data, such as purchasing or maintenance. You’ll also find some user-specific settings in the header area. For example, you can call up and manage your user profile here. It’s also possible to manage the displayed cards here.

If you want to further restrict the data displayed, you can do so using smart filter ➋, which is located below the title in the dynamic page header. For example, you can filter the data displayed so that only entries that match your filter criteria are shown, such as only certain date values, totals, and so on.

Figure 6.1: SAP Fiori Elements Overview Page
![Uploading image.png…]()


The actual content is represented by the area with the cards, also called dynamic page content ➌. Cards belong to the components of the UI that can be configured via annotations. This makes them very versatile, as data can be displayed in many different ways. All kinds of charts, tables, or lists can be displayed within a card. The cards are displayed in five dynamic columns, whereby a card can also extend over several columns. They can be arranged as desired via drag and drop.

Note that a card is always bound to exactly one entity set. For example, if you want to display a product list on a card, this can be defined in a JavaScript Object Notation (JSON) object, as shown in Listing 6.1. This object can be found in the manifest.json file of your SAP Fiori elements app. When adding a card via one of the development environments, the corresponding definition is added at the code level.

Listing 6.1: Definition of a Card in manifest.json
"sap.ovp": {
    "cards": {
        "card01": {
            "model": "ZCP_PRODUCTS_SRV",
            "template": "sap.ovp.cards.list",
            "settings": {
                "sortBy": "Price",
                "sortOrder": "descending",
                "listFlavor": "bar",
                "annotationPath": "com.sap.vocabularies.UI.v1.LineItem#bar",
                "category": "{{card01_category}}",
                "entitySet": "ProductSet"
            }
        }
    }
} 

6.1.2 Floorplans for Lists
With the list floorplans, you have the option of displaying data in list or table form. Unlike the overview page, three variants of the list floorplan are available here, which are used depending on the app:

List report

Analytical list page

Worklist

All three floorplans are ideal for presenting data in the form of lists or tables. However, there are some differences in their use, which we’ll now discuss briefly.

List Report
The list report is mainly used when large amounts of data need to be displayed and the individual entries need to be handled. The presentation doesn’t necessarily have to be in tabular or list form, and a diagram is also possible. In addition, this floorplan enables users to prepare the result set accordingly by means of filters, sorting, and grouping. In this way, large amounts of data can be reduced to the relevant records.

However, you should not use the list report if you want to see the details of a record. In this case, the object page would be suitable (Section 6.1.3).

The list report is structured as follows:

Dynamic page header

Content area

Footer toolbar

At the top of the page, you’ll find the dynamic page header mentioned earlier (Figure 6.2 ➊). This header contains the title of the report and tells you what information is displayed with the app. In addition, you’ll also find the filter line and buttons for general actions in the dynamic page header. These actions allow you to expand or compress the header. You can also pin or unpin it so that it’s always displayed or only at the top when scrolling through the list.

The content area ➋ displays the actual content in table, list, or chart form. You can display data in different ways in this area. In addition, a title and an icon tab bar are displayed above the list. The latter can contain text buttons and/or icons.

In the footer toolbar, you’ll find overarching actions that relate to the entire data overview, for example, saving or starting a simulation, as well as a notification icon, if applicable. This icon allows you to view notifications of errors that have occurred in a floating menu (popover). The footer toolbar is optional.

Figure 6.2 shows what a list report might look like. In this example, however, no footer toolbar is used—only the dynamic page header with the filter functions and the content area.

Figure 6.2: SAP Fiori Elements List Report
![image](https://github.com/user-attachments/assets/2d69f27d-246c-4232-b132-9e576992227f)


Worklist
The worklist is very similar to the list report in some respects. This floorplan is also used when large amounts of data need to be presented in list or table form. However, the data processed in a worklist differs from that of a list report. A list report displays all data. A worklist displays data on tasks that need to be completed by the user. A worklist can be used in an approval/rejection process, for example. As a rule, users can choose whether to complete a work item themselves or to delegate it.

The structure of the worklist basically corresponds to that of the list report. You’ll find the following sections here as well:

Header title

Content area

Footer toolbar

Figure 6.3 shows an example of a worklist. The header title and header tool are visible in the upper area, and the content area with several tabs is directly below. The header title ➊ for the worklist is the counterpart to the dynamic page header of the list report. However, KPIs can also be displayed here. In the content area ➋, you’ll find the table with the work items. In addition, a tab bar ➌ can be inserted to filter the displayed data via different tabs. The footer toolbar is used in the same way as the list report. Here, too, closing functions and a floating menu (popover) for notifications are available.

Figure 6.3: SAP Fiori Elements Worklist
![image](https://github.com/user-attachments/assets/9fff06c7-2fb7-475d-aa1f-d438b5e2f4b7)


Analytical List Page
The third list floorplan is the analytical list page, which offers you the possibility to display a wide variety of data in a unique way. For example, you can break down data into individual items and analyze them in different ways. To do this, you don’t have to navigate back and forth, but can stay on the same page. In addition to a simple table view, the analytical list page allows you to display selected data in charts and more detailed lists. This allows users to see all the data sets that are relevant to them at first glance. Highest and lowest values in particular, as well as deviations, can be displayed especially well.

Unlike the other two list floorplans, the analytical list page consists of only two elements:

Analytical list page header

Analytical list page content area

The analytical list page header (Figure 6.4 ➊) contains filter operations in addition to a title. You’ll also find the option to expand or compress the filter bar here. You can display data in a formatted form within the header using KPIs. The analytical list page content area ➋ contains the content of the analytical list page. This can be displayed using a wide variety of UI elements. It’s up to you whether you display the data using a table, diagram, or both.

The analytical list page is particularly useful when the app needs to provide key information about a subject or topic area at a glance. It’s often used to gain insight into the current situation and to understand how this data came about. To do this, it’s often necessary to break down data to several levels, for which the analytical list page is very well suited. If, on the other hand, it’s only a question of displaying an arbitrary list of data or the detailed view of an object, this floorplan should not be used.

Figure 6.4 shows the hybrid view of an analytical list page.

Figure 6.4: SAP Fiori Elements Analytical List Page
![image](https://github.com/user-attachments/assets/b91d0ac2-18f7-4e6b-b215-cb36b0d8e889)


In addition to a tabular representation, this also contains diagrams. The tables and the charts are based on the same data. However, in the table view the data is broken down in more detail. While in the diagram, you see the Sales Orders cumulated per customer, the tables show the individual orders of each Customer. This view provides an improved overview of this data.

6.1.3 Object Page
In the previous sections, we’ve looked at floorplans that allow data to be displayed in tables or charts. What we’re still missing is the detailed view of a business object. This is made possible by the object page. However, the functions of the object page go beyond those of a detailed view. You can also use it to create new objects, edit existing ones, or delete them. Depending on how complex your objects are, you can display the data in simple forms or in tables.

The object page is made up of the following components:

Dynamic page header

Navigation bar (optional)

Content area

Footer toolbar (optional)

The dynamic page header (Figure 6.5 ➊) contains key information about the displayed object. You’ll also find an Edit button and a Delete button here. In addition to the title, the header also contains a subtitle or breadcrumbs.

You can use the navigation bar ➋ to control which content is displayed in the content area. This can be used in two different ways:

Anchor bar
An anchor bar consists of a series of links that refer to different subsections. Clicking on such a link takes you to the corresponding subsection. The anchor bar is mainly used when the contents of the individual sections belong together.

Tab bar
The tab bar also contains links. However, these refer to other pages within the app. This form of navigation is used when different contents are displayed on the individual pages.

The available tabs are displayed in the form of horizontally arranged links. Each of these links can be used to jump to a section or subsection.

The content area displays the detailed data of an object. this representation is done by means of sections ➌ and subsections ➍. A section can be seen as a kind of container that contains several subsections. Each section has a title. In the subsections, you’ll find the actual contents. Each subsection also has a title and a toolbar. Whether you display tables, forms, or diagrams in the subsections is up to you.

Below the content area is the footer toolbar, which contains, if available, final actions such as saving, canceling, or accepting changes.

Figure 6.5 shows what an object page might look like. In the header, some important KPIs are shown here. You’ll also find actions such as editing or deleting an object, but also more specific functions. In the content area, the details of the selected object are displayed in forms and tables.

Figure 6.5: SAP Fiori Elements Object Page
![image](https://github.com/user-attachments/assets/f81e9853-6432-4412-a4d1-9357bb41eba9)


The object page should be used if you want to allow users to view, create, and edit business objects. It’s also very practical to get an overview of an object and to use some interaction possibilities.
