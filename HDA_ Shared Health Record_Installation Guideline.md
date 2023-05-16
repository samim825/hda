![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.001.png)

<a name="_1l6grp7iwn1i"></a><a name="_4clqacp8egas"></a>**Shared Health Record**

<a name="_99vxvj9cwgu"></a>**Installation & Configuration Guideline**

<a name="_4rwhyprnqia6"></a><a name="_xgjqksn08byh"></a>

<a name="_efipp47oj62z"></a>**Contents**

[**Acknowledgements	3**](#_rw7j01untj4l)**

[**Acronyms and abbreviations	3**](#_xssmvgv5aqid)

[**Executive summary	3**](#_1007ykjoltjr)

[Introduction	3](#_eu0fq0cq8pp)

[Target audience	3](#_kv5u2ywio0ai)

[Guideline development methods	3](#_jyeurqtz8kah)

[Recommendations	3](#_oa1s4guc70nn)

[**Introduction	4**](#_md9qgeeapdpw)

[**Configuration	5**](#_c2syoq6ekk0c)

[Prerequisite	5](#_kwtx9mnkr3hp)

[Add New User	6](#_32uq1fc9629l)

[Case Study	6](#_q8bucgu393ff)

[Create User Details	6](#_ezjf2492h2u8)

[Detailed Profiles	7](#_1051pjsnwfcp)

[Detailed Groups	7](#_xvk9b5b1aa9a)

[Create Password	8](#_d5fapl22qgo)

[Create Authentication Key	9](#_mdcwbs2ez24d)

[Add New Location	9](#_43iz2rs31o1e)

[Add New Facility	9](#_vsh4zebyre3s)

[Story rana	9](#_e3sodyqz48x8)

[Add new Provider	10](#_giprzs47spgi)

[Case Study / Story	10](#_zdhiqwao90ay)

[Build and publish docker images	10](#_xy6ianqfcq2)

[**Implementation	10**](#_lvytv82a9yf2)

[Prerequisite	10](#_gjh96nlaj61h)

[Installation	10](#_metf516tmbwa)

[Health ID	11](#_lyyov9lx5z2l)

[Generate Health IDs	11](#_hc6o677imkh8)

[How to generate health ID	11](#_3oilhj6j3o8)

[Add MCI Locations	13](#_istbcapddev2)

[Case Study / Story	13](#_y6zhvw53g1sg)

[How to add	13](#_mo665ty43z5m)

[Terminology Server Database	13](#_4wdbkeb9nayi)

[What is Terminology Server Database	13](#_rtx4he9jrvfj)

[Configure Terminology Server Database	13](#_tkmr0yle64lj)

[Configure Concepts in Terminology Server	17](#_bqrtg62doq0a)

[**Integration	17**](#_z36ru6mg3jr)

[Authorized User	17](#_b9osjuc3zblo)

[MCI Patient API	18](#_cgsmm9w8904v)

[Create MCI Patient	18](#_8s0zr4ej6b7w)

[Payload With Health ID	18](#_1nn4cs26iqc1)

[Payload Without Health ID	18](#_li38sjiursh)

[National ID Validation	18](#_gb5b7kfv99m4)

[Update MCI Patient	18](#_6jdu41qqwb4e)

[Search MCI Patient	18](#_9ay0a2m93gs5)

[SHR Encounter API	19](#_6dih5ao2jlf0)

[Create, Update, Fetch	19](#_837hts6wcaln)

[Encounter Payload	19](#_t0g8yxgd712o)

[XML Payload Format	19](#_qs21w1r9l988)

[JSON Payload Format	19](#_s9hr2elxp9kj)

[Valid Payload Examples	19](#_txl755bjr98d)

[FHIR Bundle Validation	20](#_nwfrmhxb6l3b)

[HAPI FHIR Validator	20](#_cz0r12sik4ng)

[Patient Validation	20](#_4let3lfl2esa)

[Health ID Reference Validation	20](#_pwbzyk6pmihl)

[Facility Reference Validation	20](#_vp6xqf9l2e0i)

[Provider Reference Validation	21](#_gl52z435ifdj)

[Resource Code Validation	21](#_74wwhbr2b9p7)

[Terminology Concept Validation	22](#_41dir5nd76vc)

[**Developers Note	22**](#_rxo7qped0rqu)

[HID Scheduler	22](#_579ji4yfrbdy)

[Search Data configuration	22](#_mzlwi1vdwe5i)

[Suggested Improvements	23](#_2ebot9zd3w1k)

# <a name="_hais5hro7uba"></a>**
# <a name="_rw7j01untj4l"></a>**Acknowledgements**
# <a name="_xssmvgv5aqid"></a>**Acronyms and abbreviations**
# <a name="_1007ykjoltjr"></a>**Executive summary**
## <a name="_eu0fq0cq8pp"></a>**Introduction**
A Shared Health Record (SHR) is a secure digital record that contains a patient's health information, such as medical history, lab results, allergies, and medication information. It is designed to allow healthcare providers and patients to access and share health information seamlessly across different healthcare settings and providers.

The goal of a SHR is to improve the coordination and quality of care by providing healthcare providers with timely access to complete and accurate health information, regardless of where the patient received care. It can also empower patients to better manage their health by providing them with access to their health information and enabling them to share it with their healthcare providers.

SHRs are typically managed by a central organization or entity, such as a health authority or government agency, that is responsible for ensuring the security and privacy of the health information contained in the record. Access to the record is restricted to authorized healthcare providers and patients, and strict protocols are in place to protect the confidentiality of the information.

In summary, SHRs have the potential to revolutionize the way healthcare is delivered by providing a seamless and secure way to share health information across different healthcare settings and providers. By improving the coordination and quality of care, SHRs can help to improve patient outcomes and reduce healthcare costs.

## <a name="_kv5u2ywio0ai"></a>**Target audience**
There are 2  types of target audience of a service or resource provider:

Systems - facilities and other DGHS systems/apps

Admins - administrators of services (example SHR, HRM or other DGHS apps etc)




## <a name="_k67rms64x5iz"></a>
## <a name="_jyeurqtz8kah"></a>**Guideline development methods**
The development of Shared Health Record (SHR) guidelines typically involves a rigorous and collaborative process that involves multiple stakeholders, including healthcare providers, patients, government agencies, and other relevant organizations. Here are some common methods used for SHR guideline development:

Systematic review: This involves a comprehensive and structured review of existing evidence and research related to SHRs, including their benefits, challenges, and best practices. A systematic review helps to ensure that the guidelines are based on the best available evidence.

Delphi method: This is a structured approach that involves soliciting and incorporating input from multiple stakeholders, such as healthcare providers and patients, through a series of surveys and feedback loops. The Delphi method helps to ensure that the guidelines are relevant, practical, and reflective of the diverse perspectives of stakeholders.

Consensus-based approach: This involves convening a panel of experts and stakeholders to develop and refine the guidelines through a series of discussions, debates, and negotiations. The consensus-based approach helps to ensure that the guidelines are reflective of the collective wisdom and expertise of the panel.

Evidence-based consensus development: This method involves combining evidence-based systematic review with a consensus-based approach to develop the guidelines. This approach helps to ensure that the guidelines are both evidence-based and reflective of stakeholder perspectives.

Overall, the development of SHR guidelines typically involves a collaborative, evidence-based approach that incorporates input from multiple stakeholders. By involving a range of perspectives and expertise, the resulting guidelines can provide a comprehensive and practical framework for the development and implementation of SHRs in healthcare.

## <a name="_oa1s4guc70nn"></a>**Recommendations**
# <a name="_w1k38wju2bh9"></a>**TBD**
#
#
#
#
#
#
#
#
#
#
#
# <a name="_9k7o98j4mjrw"></a><a name="_hkikeqhzhvef"></a><a name="_jldgczbhpw07"></a><a name="_6z05n0ibg2zt"></a><a name="_500g3ptwxvqc"></a><a name="_itmzo5ga49h9"></a><a name="_47nn9p5zzxer"></a><a name="_6yzfxioowcsy"></a><a name="_ub53co2nv03e"></a><a name="_s5rv4yk2pnaw"></a><a name="_og9nyjz6um64"></a><a name="_md9qgeeapdpw"></a>**Introduction**
[Shared Health Record](https://sharedhealth.github.io/) is an open source project developed by Thoughtworks for DGHS Bangladesh. The original source can be found in Github under the [SharedHealth](https://github.com/SharedHealth) project. There is an official [wiki](https://sharedhealth.atlassian.net/) that published by Thoughtworks has all the technical details of the project and its components.



However, a new repository has been published in Github under the [SharedHealthRecord](https://github.com/orgs/SharedHealthRecord) project. It is a fork of the original SHR components. The intention of this initiative was to fix  the configuration issues and source code bugs and apply new changes  to run the system smoothly.



The purpose of this documentation was not to replace the original SHR documentation but to focus on specific areas that are essentials to run this project. In fact, this document has not described every detail of the components since it is already written in the wiki. We recommend reading the original documentation along with this document to understand each detail perfectly. 















# <a name="_ldwdvwfqv2s5"></a>**
# <a name="_c2syoq6ekk0c"></a>**Configuration**
The configuration of a shared health record (SHR) system typically involves a series of steps to set up and customize the system to meet the needs of a particular healthcare organization or user group. Some common steps in the SHR system configuration process may include:

Installation and setup: The SHR system must be installed and configured on the appropriate hardware and software platforms. This may involve installing server software, setting up databases, configuring network settings, and configuring security settings.

User account and permission management: User accounts must be created for healthcare providers, administrators, and other users who will be accessing the SHR system. User permissions must be established to ensure that users can only access the health records and data elements that they are authorized to view or modify.

Health record management: The SHR system must be configured to manage patient health records, including data elements such as demographics, medical history, lab results, medications, and other clinical data. This may involve setting up data fields, data validation rules, data import/export settings, and other features related to health record management.

Clinical workflow management: The SHR system must be configured to support the clinical workflows and processes of the healthcare organization or user group. This may involve setting up templates for clinical notes, configuring order entry screens, and setting up alerts or notifications for important events or tasks.

Reporting and analytics: The SHR system must be configured to generate reports and analytics that provide insights into the healthcare organization's clinical and operational performance. This may involve setting up dashboards, configuring report templates, and setting up data visualization tools.

Integration with other systems: The SHR system may need to be integrated with other healthcare information systems, such as electronic health record (EHR) systems, lab information systems, or imaging systems. This may involve setting up data exchange protocols, configuring APIs, or establishing other interfaces between the SHR system and other systems.

Overall, the configuration of a shared health record system is a complex and iterative process that requires close collaboration between IT staff, clinical staff, and other stakeholders. Effective configuration can help to ensure that the SHR system meets the needs of the healthcare organization and supports high-quality, coordinated care delivery.

*This section is only required when the SHR components will be run in the staging or production mode.*

*To run the components in development mode, it is enough to follow the Readme of the HIE Docker repository.*


## <a name="_kwtx9mnkr3hp"></a>**Prerequisite**
- Docker
- Java 8
- Git

The current system doesn’t have any user management service. Instead it offers a very simple Authentication and Authorization mechanism by hard-coding user details, password, facilities and locations in the **Identity Server**. Some details about the Identity Provider:

- All systems making any HIE api call (except for Terminology Service) must have an "API Token". This token must be passed as an "X-Auth-Token" header while making an API request. To put in a very simplistic fashion, the following are the authentication steps:
- The system and a user account for the system must be set up in the central Identity Provider (IdP). Please see the documentation regarding onboarding a system/facility for SHR integration.
- This is an offline process: an organization will request the authority (DGHS) for access to HIE (naming the components that they want to access) with the intended purpose. There will be policies that the participating organization will have to comply with and upon resolution of such aspects, the authority will grant access to the organization. 
- Once the setup is done, the organization will be given the following details
  - *API Token* - this is a long living token and disclosed to and used only by organizations who have gone through the above procedure.
  - *client\_id* - disclosed only to the organization, and this must be communicated with every API request
  - registered email and password for the user of that organization
 
- To get an "access\_token" from the central Identity Provider (IdP):
  - Make an HTTP POST to the IdP login api. See below for info
  - An "access\_token" will be returned. This access token is short lived and can be invalidated too by the user. 
- Make service calls with the "access\_token" passed.
- Subsequent API calls to any HIE services, should pass only the "access\_token". Note, at no point should you be sending your "API TOKEN" to any other service other than the IdP login service.

**Authorization**

Each service is responsible for deciding on authorization independently. This authorization decision depends on requesters profiles setup in IdP.  For example, an organization can have rights to create a patient but not a clinical encounter. See below for more information

**Additional details**

- Even trusted systems like SHR or MCI or other DGHS apps, must register themselves with the HRM system as organizations. for example as "SHR @ DGHS MIS" or "MCI @ DGHS MIS".  An api token is created for systems and provided and configured with the system beforehand.
- ` `Any invalid request with non-matching *client\_id* and *X-Auth-Token*, will result in HTTP 401 (unauthorized) error.


**IdP API details**

1. **Login using IdP API**

   Request :
   POST http://{IdP-URL}/api/1.0/sso/signin
   Headers :
   client\_id = {client id of the user representing the organization}
   X-Auth-Token = {Secret API Token given to the user representing the Organization}

   Form Data :
   email = {user email}
   password = {user password}


   ` `**Example response on successful login (HTTP Status code 200)**

   {
   `  `"access\_token": "UXmbhELOU47hC5bA7rvvtx2lMuePIF1kOTgyVAhcAX",
   }

   **Example response on failed login (HTTP STATUS code 404)**

   {
   `   `"error": true,
   `   `"message": "Not authenticated",
   `   `"code": 401
   }
1. **Logout using IdP API** 

   Request :
   POST http://{IdP-URL}/api/1.0/sso/signout/{access\_token}
   Headers :
   client\_id = {client id of the user representing the organization}
   X-Auth-Token = {Secret API Token given to the user representing the Organization}
   content-type :application/x-www-form-urlencoded
   Form Data :
   email = {user email}
   password = {user password}
 
1. **Get user info from access token**
   Request :
   GET http://{IdP-URL}/api/1.0/sso/token/{access\_token}
   Headers :
   client\_id = {client id of the user representing the organization}
   X-Auth-Token = {Secret API Token given to the user representing the Organization}

**Accessing a service/resource provider**
As explained earlier, once an "access\_token" is received, you may call other [HIE APIs](https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/524336/HIE+Components). All API calls must accompany the following details.
with headers:  

client\_id = (client id of the user representing the organization)

X-Auth-Token = (access token fetched earlier)

from = (email id of the requester, one that's used for login)

**More on authorization**

There are 4 types of requester of a service or resource provider:

systems - facilities and other DGHS systems/apps

providers - CHWs, doctors etc

admins - administrators of services (example SHR, HRM or other DGHS apps etc)

individual users - patients

The above can be broadly categorized into human (provider, admin, individual users) and non-human users (facilities, other DGHS systems/apps)

A user can have multiple profiles; example: a user can be a provider, a patient herself. or a user can be a patient while he/she can be an administrator of a particular region.

IdP (HRM) will have such user/client information as profiles; so that each user can have multiple profiles. The service/resource provider makes its own decision to authorize a request based on the user profile and groups the user is associated with.



Identifying the catchment of a requester

Many services and applications like SHR, MCI, MCI admin applications need to find out the catchment of the requester to allow operations limited only to the catchment defined for the requester. For example: a facility can sync only their catchment patients, or MCI admins can approve updates only for patients in their defined catchment areas. IdP may send the catchment information as part of the profile info.

- Systems (facilities, DGHS apps etc) - Each facility depending on its location and type has a catchment defined for it in the facility registry. By default this is determined by the type of facility and their physical location, unless overridden.
- Providers - If the requester is attached to a facility, then their catchment is that of the facility (as explained above) unless overridden. 
- Admins (administrators of services like SHR, HRM or other DGHS apps etc) - are associated with administrative areas.
- Individual user (patient) - no catchment is defined.

For example: the following userinfo may be returned to the service provider, when they try to identify the requester (example, someone is trying to create/POST a patient). Note the profiles associated. 

|<p>{</p><p>`    `"id": 6,</p><p>`    `"name": “Dr. X Y Z”,</p><p>`    `"email": "xyz@gmail.com",</p><p>`    `"is\_active" : **true**,   </p><p>`    `"activated": **true**,</p><p>`    `"activated\_at": **null**,</p><p>`    `"last\_login": "2015-01-20 09:52:58",</p><p>`    `"access\_token": "xyz\_token",</p><p>`    `"created\_at": "2014-09-04 13:26:14",</p><p>`    `"updated\_at": "2015-01-20 09:52:58",</p><p>`    `"deleted\_at": **null**,</p><p>`    `"groups": ["MCI Admin", "API Consumer"],</p><p>`    `**"profiles": [**</p><p>`      `**{**</p><p>`         `**type: "provider",**</p><p>`         `**id: "123",**</p><p>`         `**catchment: ["302618","302614"]**</p><p>`      `**},**</p><p>`      `**{**</p><p>`         `**type: "admin",**</p><p>`         `**id: "2",**</p><p>`         `**catchment: ["3026"]**</p><p>`      `**},**</p><p>`      `**{**</p><p>`         `**type: "facility",**</p><p>`         `**id: "10000069",**</p><p>`         `**catchment: ["302618"]**</p><p>`      `**},**</p><p>`      `**{**</p><p>`         `**type: "patient",**</p><p>`         `**id: "10091232131",**</p><p>`         `**catchment: []**</p><p>`      `**}**</p><p>`    `**]**</p><p>}</p>|
| - |


Reference link: 

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/24641543/Identiy+Provider>

The Identity Server repository has included some default users, locations and facilities. To add a new user or location or facility, we have to download the Identity Server source code from [Github](https://github.com/SharedHealthRecord/Identity-Server). We can clone the source code using the following git command:

[git clone https://github.com/SharedHealthRecord/Identity-Server.git](https://github.com/SharedHealthRecord/Identity-Server.git)
##
## <a name="_hviacwbj7gcs"></a><a name="_b70kpr5syr7o"></a>
## <a name="_32uq1fc9629l"></a>**User**

In a shared health record (SHR), there can be different types of users depending on their role and level of access. Here are some common types of users that can be found in an SHR:

Patients: These are individuals who receive healthcare services and have their health information recorded in the SHR. Patients can access their own health records to view their health information and share it with healthcare providers as needed.

Clinicians: These are healthcare providers, such as doctors, nurses, and therapists, who use the SHR to access patient information, document care, and coordinate care with other providers. Clinicians may have different levels of access to the SHR, depending on their role and responsibilities.

Administrators: These are individuals who are responsible for managing the SHR, including setting up user accounts, managing access permissions, and maintaining the security of the system.

Researchers: These are individuals who use the SHR for research purposes, such as analyzing health trends, evaluating treatments, or developing new interventions. Researchers may have access to de-identified patient data, but must adhere to strict ethical and legal guidelines to protect patient privacy.

Public health officials: These are individuals who use the SHR to monitor and respond to public health issues, such as disease outbreaks or environmental hazards. Public health officials may have access to aggregated data from the SHR to identify patterns and trends.

Health information exchange (HIE) coordinators: These are individuals who manage the exchange of health information between different healthcare organizations using the SHR. HIE coordinators work to ensure that patient information is shared securely and accurately between different providers and systems.

It's important to note that the specific types of users in an SHR may vary depending on the system and the healthcare organization using it.


This Guideline shows the following 3 types of user addition:

systems :  facilities and other DGHS systems/apps

providers :  CHWs, doctors etc

individual users :  patients


**Add New User**

Adding a new user to a shared health record (SHR) would depend on the specific SHR platform being used. In general, adding a new user to a SHR would require administrative privileges and access to the platform's user management system.

The exact steps to add a new user may vary depending on the SHR platform, but some general steps that may be involved include:

- Accessing the user management system of the SHR platform.
- Selecting the option to add a new user.
- Providing the new user's information, such as their name, email address, and role (e.g., patient, clinician, administrator).
- Setting the user's permissions and access levels.
- Verifying the new user's identity and authorizing their access to the SHR platform.

It's important to note that adding a new user to a SHR involves handling sensitive and confidential information, so it's crucial to follow the proper protocols and security measures to ensure the privacy and security of the shared health record.

To create a new user, we have to modify the following three properties files in the Identity Server:

1. userDetail.properties
1. userPassword.properties
1. clients.properties

### <a name="_ocwtsz3yso2i"></a>
###
### <a name="_r7jci8rl0dye"></a><a name="_ezjf2492h2u8"></a>**userDetail.properties**
In a shared health record (SHR), the "userDetail.properties" file (or a similar configuration file) may contain information about a user's account or profile within the SHR system. This file may include details such as:

test-new-user@test.com={"id": "18001","name": "Local Facility Admin","email": "test-new-user@test.com","groups": ["Facility Admin","SHR User","MCI User"],"profiles": [{"name": "facility","id": "10019871","catchment": ["3026"]}]}


|**Key**|**Note**|
| - | - |
|id|A uniquely identified value|
|name|Name of the user|
|email|Email of the user|
|groups|List of user roles|
|profiles|List of user profiles. |


"profiles": [{"name": "facility","id": "10019871","catchment": ["3026"]}]

|**Key**|**Note**|
| - | - |
|name|This identifies the user profile type. This can be facility/mci-supervisor/provider/patient.|
|id|<p>ID could be either of the followings:</p><p>- a valid facility ID</p><p>- mci-supervisor ID from userDetails properties</p><p>- a valid provider ID</p><p>- valid patient Health.</p>|
|catchments |List of catchments. Catchments must be valid location IDs.|

"groups": ["Facility Admin","SHR User","MCI User"]

|**Group Name**|**Details**|
| - | - |
|Facility Admin|<p>- Creating a New Patient</p><p>- Find Patient by HealthId</p><p>- Find all Patients by search query</p><p>- Updating Patient with HealthId</p><p>- Find all Patients by Catchment</p><p>- Find all Patients using updated since date and last marker</p>|
|MCI Admin|<p>- Find Patient by HealthId</p><p>- Find all Patients by search query</p><p>- Updating Patient with HealthId</p><p>- Find list of locations by parent</p><p>- Find audit details of patient by healthId</p>|
|MCI Approver|<p>- Find Patient by HealthId</p><p>- Find list of pending approvals for catchment</p><p>- Find list of pending approvals details for patient</p><p>- Accepting pending approvals for patient</p><p>- Rejecting pending approval for patient</p><p>- Find list for Patient duplicates for catchment</p><p>- Merge/Retain two duplicate patients</p><p>- Updating to merge duplicate Patients</p><p>- Find list of locations by parent</p>|
|SHR System Admin|<p>- Generating new Health Ids for all URI</p><p>- Generating new Health ids for block URI</p><p>- Generating new Health ids for Organisation</p><p>- Assigning next block Health ids for MCI</p><p>- Marking Health Id as used</p><p>- Checking availability of Health Id for an organization</p><p>- Find Patient by HealthId</p><p>- Find All Encounters of patient</p><p>- Find an Encounter for a patient</p><p>- Find all Patients using updated since date and last marker</p><p>- Find all Patients by Catchment</p><p>- Find all Encounters for Facility in Catchment</p>|
|Provider|<p>- Creating a New Patient</p><p>- Find a Patient by Health Id</p><p>- Find all Patients by search query</p><p>- Updating Patient with HealthId</p><p>- Find all Patient by Catchment</p><p>- Create Encounter for Patient</p><p>- Update Encounter for Patient</p><p>- Find an Encounter for Patient</p><p>- Find all Encounter of Patient</p><p>- Find all Encounter for Facility in Catchment</p>|
|Patient|<p>- Find Patient by Health Id</p><p>- Find all Encounters of a specific patient using healthId</p><p>- Find a specific Encounter for a specific  patient using  healthId and encounterId</p>|


### <a name="_d5fapl22qgo"></a>**userPassword.properties**
The "userPassword.properties" file in a shared health record (SHR) system is a configuration file that typically contains information related to user authentication and password management. Specifically, it includes:

test-new-user@test.com=password
### <a name="_mdcwbs2ez24d"></a>**Create Authentication Key**
Finally, an authentication token has to be added in the **clients.properties** file against the id of the user. For example:

18001=test-new-user\_auth\_token

***Note:** 18001 is the User ID that is defined in the userDetails.properties file.*

## <a name="_43iz2rs31o1e"></a>**Add New Location**

The purpose of location is to uniquely identify geographical locations in a country - often in terms of administrative setup. This allows them to identify patients location and care services location uniquely.


Location as required for creating a new user. Location IDs are used as catchment in the user profile. To create a new location, we have to create a new json file in the resources/locations folder. The json name will be {geoCode}.json. Details about location registry: 

**Get Locations**

Request :

GET https://{lr\_service}/locations/list/{level}?updatedSince={ISO8601 formatted date}&limit={limit}&offset={offset}

Headers :

X-Auth-Token : {auth token assigned while user registration in HRM}

client\_id : {client id of requester in Identity Service Provider}

The level field can contain one of the following :

1. division
1. district
1. upazila
1. paurasava
1. union
1. Ward

Sample Response

[

`  `{

`    `"code": "1020",

`    `"id": "1020",

`    `"name": "Example Location",

`    `"name\_BN": "",

`    `"type": "district",

`    `"active": 1,

`    `"updatedAt": "2016-10-02 13:19:57",

`    `"hierarchy": [

`      `{

`        `"code": "10",

`        `"name": "Example Parent Location",

`        `"name\_BN": "",

`        `"type": "division"

`      `},

`      `{

`        `"code": "20",

`        `"name": "Example Location",

`        `"name\_BN": "",

`        `"type": "district"

`      `}

`    `]

`  `}

]

Reference link:

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/524414/Location+Registry>

## <a name="_vsh4zebyre3s"></a>**Add New Facility**
All institutions like hospitals, clinics or health service centers are called facilities.

Facilities are associated with the user. To create a new facility, we have to create a new json file in the resources/facilities folder. The json file name must be {facility\_code}.json. Facility registry details:

**Get Facilities**

Request :

GET [{fr_server}/facilities/list?limit={limit}&offset={offset}&updatedSince={ISO8601 formatted date}](http://hrmtest.dghs.gov.bd/api/1.0/facilities/list?limit=1&offset=1&updatedSince=2015-01-01)

Headers :

X-Auth-Token : {auth token assigned while user registration in HRM}

client\_id : {client id of requester in Identity Service Provider}

` `Sample Response

[

`  `{

`    `"code": "1020",

`    `"id": "1020",

`    `"name": "Example Location",

`    `"name\_BN": "",

`    `"type": "district",

`    `"active": 1,

`    `"updatedAt": "2016-10-02 13:19:57",

`    `"hierarchy": [

`      `{

`        `"code": "10",

`        `"name": "Example Parent Location",

`        `"name\_BN": "",

`        `"type": "division"

`      `},

`      `{

`        `"code": "20",

`        `"name": "Example Location",

`        `"name\_BN": "",

`        `"type": "district"

`      `}

`    `]

`  `}

]

Reference link:

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/524401/Facility+Registry>

## <a name="_giprzs47spgi"></a>**Add new Provider**
In "HIE" context, the provider describes "who provides services" to a patient. In a shared health record (SHR) system, a provider typically refers to a healthcare professional who provides clinical care to patients, such as a physician, nurse, or therapist. Providers are important users of SHR systems, as they use these systems to access and manage patient health information as part of their clinical workflows.

Providers may have different levels of access and permissions within the SHR system, depending on their role and responsibilities. For example, a physician may have access to a patient's full medical history and be able to make diagnoses and treatment decisions based on this information, while a nurse may have more limited access and be primarily responsible for documenting patient vital signs and administering medications.

A new Provider can be added. A new Json with a name like {provider-id}.json must be saved in the resources/providers folder. The provider registry details can be found in the following link: 

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/524422/Provider+Registry>

## <a name="_xy6ianqfcq2"></a>**Build and publish docker images**
After changing the source code, it is required to build the application and create the docker image to deploy the changes.

Build identity-server

./gradlew clean dist -x test

Then, we have to clone the HIE-Docker repository (if it is not cloned yet):

git clone https://github.com/SharedHealthRecord/HIE-Docker.git

cd HIE-Docker

#Build docker image

docker compose build identity-server

#Push docker image to DockerHub

docker compose push identity-server
# <a name="_bbjsglixfi5p"></a>**
# <a name="_lvytv82a9yf2"></a>**Implementation**

## <a name="_gjh96nlaj61h"></a>**Prerequisite**
Docker

Git


## <a name="_metf516tmbwa"></a>**Installation**
- git clone https://github.com/SharedHealthRecord/HIE-Docker.git
- cd HIE-Docker
- ./run-shr-cluster.sh

## <a name="_lyyov9lx5z2l"></a>**Health ID**
##
<a name="_oa2hh542cug8"></a>Health id is a unique identifier. This identifier is generated from a central HID service. It is a randomly generated 11-digits number that will enable one to access and share records admission to treatment.

## <a name="_hc6o677imkh8"></a>**Generate Health IDs**

## <a name="_3oilhj6j3o8"></a>How to generate health ID
Some details about the Health ID generation are described here: <https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/24641563/Health+ID+Management>

The above document has all the necessary information about Health ID. We are rephrasing it here:

The following API will generate 98 and 99 series on demand Health IDs for MCI. It will generate about 199999999 Health IDs.

POST http://{healthID\_server\_url}/healthIds/generate 


This following API will also generate on demand Health IDs for MCI. But in this case it will generate only 10 IDs starting from 9800000221

POST http://{healthID\_server\_url}/healthIds/generateBlock?start=9800000221&totalHIDs=10


The last API generates Health IDs for a specific organization. This will generate 10 Health IDs starting from 9100000221 against the org value. The org value must be a valid facility ID that will be verified in the Identity Server.

POST http://{healthID\_server\_url}/healthIds/generateBlockForOrg?org={value}&start=9100000221&totalHIDs=10

Only SHR System Admin users have access to these APIs. It is required to get the access token for accessing these APIs. Users can follow the [link](https://github.com/SharedHealthRecord/HIE-Docker#generate-health-ids) to get the access token. Details about the sign in process are described in the following wiki:

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/24641543/Identiy+Provider>

Here is an example of getting access token from Identity Server:

curl http://localhost:8084/signin -H "X-Auth-Token:local-shr-system-admin\_auth\_token" -H "client\_id:18700" --form "email=local-shr-system-admin@test.com" --form "password=password"

After getting the access token, it must be applied to consume the Health ID APIs. A sample call could be like the following:

curl -X POST

'http://localhost:8086/healthIds/generateBlock?start=9800000100&totalHIDs=100' -H 'From: local-shr-system-admin@test.com' -H 'X-Auth-Token: <ACCESS-TOKEN-FROM-ABOVE-STEP>' -H 'client\_id: 18700'


## <a name="_o5j5mw5jiq3"></a>
## <a name="_istbcapddev2"></a>**Add MCI Locations**

## <a name="_mo665ty43z5m"></a>How to add: 
It is required to set up Locations in the MCI service to create a patient and validating patient address. The current system is to create a cql file in any location and add the locations as cassandra query language. A sample location setup is described in Github already. Please follow this [link](https://github.com/SharedHealthRecord/HIE-Docker#insert-mci-locations-).

A sample cql query will be look like below:

INSERT INTO locations ("code", "name", "active","parent") VALUES ('10','BARISAL','1','00') IF NOT EXISTS;

Here,

*code*:  Geo code  of BARISAL defined by Bangladesh Bureau of Statistics (BBS).

*name*: Name of the geo location

*active*: If this location is officially active then 1, otherwise 0.

*parent*: Geo code of the parent location

After saving the cql file, we have to execute the following commands to insert the locations in database:

docker cp path/of/the/mci\_locations.cql cassandra-seed:/tmp

docker exec cassandra-seed /bin/bash -c "cqlsh -k mci -f /tmp/mci\_locations.cql"

## <a name="_obbu0ql2xei3"></a>
## <a name="_4wdbkeb9nayi"></a>**Terminology Server Database**

### <a name="_rtx4he9jrvfj"></a>What is Terminology Server Database

Terminology Server is nothing but an instance of OpenMRS. OpenMRS has to be configured before using this as a service. The configuration steps are done by following its installation wizard.
###

### <a name="_348b4y7uqt8b"></a><a name="_tkmr0yle64lj"></a>Configure Terminology Server Database

However, we often noticed that the default installation process of OpenMRS failed. We found a workaround to make it successful:

*Step 1*: Please confirm the Terminology Server is running before proceeding.

*Step 2*: A default database name “terminologies” was created in MySQL database. Delete the database first. 

*Step 3*: Create the same database as a root user.

Now you are ready to follow the installation steps. Please go to the following link: [http://{tr_server_ip}:9080/openmrs](about:blank).  It should show you the OpenMRS installation wizard:

![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.002.png)

Click on the “Next” Icon, it will take you to the following link page. Select “Advanced” and click on “Next”.

![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.003.png)



Step 1 of 5: select “Yes” and change the Database name to “terminologies”.

![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.004.png)




Step 2 of 5: select “Yes” and type the root user credentials.

![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.005.png)


Step 3 of 5: Nothing to change. Click “Next”

Step 4 of 5: Type “Admin123” in the password field.

![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.006.png)

Step 5 of 5: Nothing to change. Click “Next”

A similar review page will be shown.

![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.007.png)

Then it will show the installation progress.

![](Aspose.Words.29d2f676-c557-4fcf-bb76-d5b92e919150.008.png)

If the installation process is successful, it should show the OpenMRS login screen. Sometimes we notice it shows the 404 page. We notice, after restarting the server, it shows the login screen.

## <a name="_bqrtg62doq0a"></a>**Configure Concepts in the Terminology Server**
It is required to add the existing concepts in the TR server to create SHR encounters.  


#
# <a name="_xnkmsqr3rcbt"></a><a name="_z36ru6mg3jr"></a>**Integration**
We highly recommend following the official documentation to know about the [Master Client Index](https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/524352/Master+Client+Index).

## <a name="_b9osjuc3zblo"></a>**Authorized User**
Facility admin users can consume the MCI Patient and Encounter APIs.  The details of the authentication process has been explained in the official wiki under the [Identity Server](https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/24641543/Identiy+Provider) page. Here is an example:

curl http://localhost:8084/signin \

-H "X-Auth-Token:local-facility-admin\_auth\_token" \

-H "client\_id:18701" \

--form "email=local-facility-admin@test.com" \

--form "password=password"

After getting the access token, the user will apply the token to consume API. For example:

curl -X POST \

`  `http://{mci\_server\_base\_url}/api/v1/patients \

`  `-H 'Content-Type: application/json' \

`  `-H 'From: local-facility-admin@test.com' \

`  `-H 'X-Auth-Token: <ACCESS-TOKEN>' \

`  `-H 'client\_id: 18701' \

`  `-d '{

…

}'

## <a name="_qaa9tfdynq1z"></a>
## <a name="_cgsmm9w8904v"></a>**MCI Patient API**
### <a name="_8s0zr4ej6b7w"></a>**Create MCI Patient**
There is already in depth documentation available in the following wiki pages. 

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/48201730/MCI+Patient+APIs>

Detail patient payload validations are also available here:

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/48201741/MCI+Patient+Create+Validations>

#### <a name="_1nn4cs26iqc1"></a>**Payload With Health ID**
If a patient payload contains the “hid”, the patient will be registered with this Health ID. Before assigning this Health ID, the system will verify whether the mentioned Health ID is pre allocated for the organization or not.
#### <a name="_li38sjiursh"></a>**Payload Without Health ID**
If there is no hid present in the patient payload, the system will register the patient with the on demand Health ID.
#### <a name="_gb5b7kfv99m4"></a>**National ID Validation**
The National ID validation has been changed in the new system. It allows 10 digits also.

### <a name="_6jdu41qqwb4e"></a>**Update MCI Patient**
Details about updating MCI Patient can be found in the following wiki page:

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/2654251/Update+Patient+API>

### <a name="_9ay0a2m93gs5"></a>**Search MCI Patient**
Details about searching MCI Patient can be found in the following wiki page:

<https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/6258714/MCI+Search+API>

## <a name="_6dih5ao2jlf0"></a>**SHR Encounter API**
The details about SHR could be found in the wiki under the [Shared Health Record](https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/524346/Shared+Health+Record) page. In this section we have explained a few changes we made in the system.

### <a name="_837hts6wcaln"></a>**Create, Update, Fetch**
We are not going to explain the create, update and fetch API in this section because these are already described in the wiki under [SHR Encounter API](https://sharedhealth.atlassian.net/wiki/spaces/docs/pages/524348/SHR+Encounter+API) page.

### <a name="_t0g8yxgd712o"></a>**Encounter Payload**
The Encounter Create and Update APIs accept XML and JSON as payload. If the encounter payload is in XML format, the FHIR bundle will have to be in XML and same rule for JSON. Only difference is, if we use JSON, we have to convert the FHIR JSON document to String, then add it to the payload against the “content” key.
#### <a name="_qs21w1r9l988"></a>**XML Payload Format**
<encounter>

<content>

<![CDATA[

`  `**<Bundle> … </Bundle>**

]]>

</content>

</encounter>
#### <a name="_s9hr2elxp9kj"></a>**JSON Payload Format**
{

`   `"content": "**{\"resourceType\":\"Bundle\"...}**"

}
#### <a name="_txl755bjr98d"></a>**Valid Payload Examples**
Example of different types of encounter are available it the following Github link:

<https://github.com/SharedHealthRecord/FreeSHR/tree/master/shr/src/test/resources/xmls/encounters>

### <a name="_nwfrmhxb6l3b"></a>FHIR Bundle Validation
#### <a name="_cz0r12sik4ng"></a>HAPI FHIR Validator
SHR systems FHIR documents are compatible with STU3 [release v3.0.0](http://hl7.org/fhir/history.html#v3.0.0). It has used the following HAPI FHIR libraries for validation FHIR documents :

hapi\_fhir\_base       : ca.uhn.hapi.fhir:hapi-fhir-base:2.3,

hapi\_fhir\_structures : ca.uhn.hapi.fhir:hapi-fhir-structures-dstu3:2.3,

hapi\_fhir\_validation\_resources : ca.uhn.hapi.fhir:hapi-fhir-validation-resources-dstu3:2.3


**IMPORTANT**: Whoever will be creating FHIR documents, must ensure these are compatible with STU3 version and pass the HAPI FHIR validation.

#### <a name="_4let3lfl2esa"></a>**Patient Validation**
The system validates patients in the MCI server using the Health ID provided with the API call.

#### <a name="_pwbzyk6pmihl"></a>**Health ID Reference Validation**
If a patient is used as a reference, the system will validate the reference URL. For example:

<subject>

`     `<reference value="http://mci.twhosted.com/api/v1/patients/98224850190"/>

`     `<display value="Abdul Karim"/>

</subject>

Here, http://mci.twhosted.com is the base url of the MCI server. The reference URL will have to be exactly the same the system has used. This means, whoever is creating this document, must know that is the MCI server url.


#### <a name="_vp6xqf9l2e0i"></a>**Facility Reference Validation**
If a facility is used as a reference, the system will validate the reference URL. For example:

<serviceProvider>

`   `<reference value="http://fr.twhosted.com/api/1.0/facilities/10019842.json"/>

</serviceProvider>

Here, http://fr.twhosted.com is the base url of the Facility Registry (FR) server. The reference URL will have to be exactly the same the system has used. This means, whoever is creating this document, must know that is the FR server url.

####
#### <a name="_u3ff3tji2581"></a><a name="_gl52z435ifdj"></a>**Provider Reference Validation**
When a provider is used as a reference, the system will validate the reference URL. For example:

<participant>

`   `<individual>

`       `<reference value="http://pr.twhosted.com/api/1.0/providers/20.json"/>

`   `</individual>

</participant>

Here, http://pr.twhosted.com is the base url of the Provider Registry (PR) server. The reference URL will have to be exactly the same the system has used. This means, whoever is creating this document, must know that is the PR server url.

#### <a name="_74wwhbr2b9p7"></a>**Resource Code Validation**
Each resource in the entries must have the coding. The system scans through all the resources and validates if coding exists. Here is an example of a coding structure:

<code>

` `<coding>

`   `<system value="http://tr.twhosted.com/openmrs/ws/rest/v1/tr/referenceterms/2218636a-0ef0-4fb1-ac7e-cf2a915b0ee4"/>

`   `<code value="J11.1"/>

`   `<display value="Influenza due to unidentified influenza virus with other respiratory manifestations"/>

` `</coding>

</code>

#### <a name="_41dir5nd76vc"></a>Terminology Concept Validation
Terminology concept will be validated through Terminology Registry (TR) server.

<name>

`     `<coding>

`       `<system value="http://tr.twhosted.com/openmrs/ws/rest/v1/tr/concepts/a1257651-7473-4c9b-bb0a-1244c5f3c09d"/>

`       `<code value="a1257651-7473-4c9b-bb0a-1244c5f3c09d"/>

`       `<display value="Temperature"/>

`     `</coding>

</name>

Here, http://tr.twhosted.com is the base url of the Terminology Registry (TR) server. This means, whoever is creating this document, must know that is the TR server url.



# <a name="_rxo7qped0rqu"></a>**Developers Note**
## <a name="_579ji4yfrbdy"></a>**HID Scheduler**
We can generate on demand Health ID for MCI. This scheduler manages the on demand Health IDs in the MCI server.

The scheduler runs every one minute. It checks if the total number of unused Health IDs is less than 15 on that time it takes the next block of Health IDs from the HealthID server. In a busy moment, there could be a chance that all the Health IDs will be assigned within one minute before the scheduler is revoked. In that case the server will respond with error and no patient will be registered.

## <a name="_mzlwi1vdwe5i"></a>**Search Data configuration**
To enable Patient search data it is required to set the flag “IS\_MASTER\_NODE '' to true in the local.properties (for local build) and env\_docker (for docker build) of the MCI-Server repository.


## <a name="_2ebot9zd3w1k"></a>**Suggested Improvements**
This system was developed almost 10 years back and last time it was updated in 2017 between 2018. The main technical expertise is missing now. The only resources are the wiki and the source code. Based on that analysis we tried to list down a few improvements but these are not everything. There are a lot of areas that can be improved in the overall infrastructure before we launch it on a national level. 

1. Cluster Support: This system is not fully cluster supported.
   1. The Cassandra database must be a separate cluster. It is running inside a docker container which is not scalable.
   1. MySQL for TR server is also running inside a docker container. It is always recemented to run database servers separately instead of running inside a docker container.
   1. Extract configuration from docker image and set those through environment variables.
   1. Schedulers must be handled carefully in a cluster setup.
1. This system will handle the health data of 16 crore people. Data security and data access mechanisms should be redesigned. 
1. HRM integration: As we described before the system has no user management. It is highly recommended to integrate with a new or existing HRM system or if there is no system.Either case, it will require few configuration and system code changes.
1. FHIR version should be upgraded to the latest version.
1. There is an Admin UI available in the original repositories but the technologies that have been used in the system are already obsolete. We must build a new Admin UI from scratch.
*Shared Health Record: Configuration & Implementation Guideline*					
