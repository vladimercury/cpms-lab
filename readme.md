# **CORPORATE PROJECT MANAGEMENT SYSTEM**

# Main goals
* Managing IT company projects
* Communication between customers and project members
* Providing information about projects to customers
* Providing deployments for customers
* Logging project changes

# Roles
* `any` any user in the system
* `member` member of the project (any user assigned to the project but not a project manager)
* `manager` manager of the project
* `owner` creator/owner of the entity
* `recipient` message recipient
* `admin` system admin

# Entities

* `User`
* `UserInfo` basic information about user
* `EmployeePosition` employee's position in the company
* `Project`
* `ProjectType` type of the project like "traditional" or "scrum"
* `ProjectRole` role of the member in the project: "customer", "manager", "developer", etc.
* `ProjectStage` stage of the project
* `ProjectStageTemplate` typical project stages like "development" or "sprint"
* `ProjectLog` represents history of changes in the project
* `Deployment` represents any working program instance or sth like project documentation, test reports, etc.
* `Message` helps to communicate between users, especially between customers and project members

# Functional requirements
## Users
* Authenticate `any`
* Create / remove user `admin`
* Edit user's info `owner` `admin`
* View any user's info `any`
## Employee positions
* Create / edit / remove position `admin`
* View positions `any`
## Projects
* Assign / unassign manager `admin`
* Assign / unassign member `manager` `admin`
* Change member role `manager` `admin`
* Create / remove project `admin`
* Edit basic project info `manager` `admin`
* Make a member a manager `admin`
* Make a manager a member `admin`
* View basic project info `any`
* View users assigned to the project `any`
## Project stages
* Assign / unassign user `manager` `admin`
* Create / edit / remove project stage `manager` `admin`
## Project stage templates
* Associate template with project type `admin`
* Create / edit / remove template `admin`
* View templates `any`
## Project types
* Create / edit / remove project type `admin`
* View project types `any`
## Deployments
* Create deployment `member` `manager` `admin`
* Edit / remove deployment `owner` `manager` `admin`
## Project log
* View project history `member` `manager` `admin`
* Create / edit / remove log record `admin`
## Log types
* Create / edit / remove log type `admin`
* View log types `any`
## Message
* Make message read `recipient`
* Send new message `any`
* View message `owner` `recipient`