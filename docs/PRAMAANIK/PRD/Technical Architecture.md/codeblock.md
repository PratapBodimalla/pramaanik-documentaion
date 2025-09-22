---
sidebar_position: 4
---

# Architecture DSl Code

https://structurizr.com/dsl

```dsl
workspace "PRAMAANIK-AI" "AI-enabled 360° professional profiling and scoring platform" {

    !identifiers hierarchical

    model {
        userStudent = person "Student" "Students"
        userFaculty = person "Faculty"
        userInstitute = person "Institutes" "Schools & Colleges"
        userIndustry = person "Inductry" "Recruiters & Employers"
        userPolicy = person "Policy Makers" "State or Central Givernments of India"
        userAdmin = person "Admin"    

        idp = softwareSystem "Identify Data Providers" "Active Directory" {
            tags "External"
        }
        trainingCertificationProvider = softwareSystem "Training and Certification Providers" "Coursera, Udemy..." {
            tags "External"
        }      
        knowledgeBases = softwareSystem "External Knowledge Sources" "Naukri, zerotomastery.io ..." {
            tags "External"
        }    
        sendemails = softwareSystem "Send Emails" "Send Email Notifications to Users" {
            tags "External"
        }         

        pramaanik = softwareSystem "pramaanik.ai" "AI-enabled 360° professional profiling and scoring platform" {
            studentUI = container "Student Web APP (PWA)" "Delivers Static Web Content" "Next js, React, SchadCN, axios"
            facultyUI = container "Faculty Web APP" "Next js, React, SchadCN, axios"
            instituteUI = container "Institute Web APP" "Next js, React, SchadCN, axios"
            inductryUI = container "Industry Web APP" "Next js, React, SchadCN, axios"
            policyUI = container "Policy Web APP" "Next js, React, SchadCN, axios"
            adminUI = container "Admin Web APP" "Next js, React, SchadCN, axios"
            
            studentDashboardPage = container "Student Dashboard Page" "Provides all of the prammanik functionality to students via their web browser" "Next js, React, SchadCN, axios"{
                tags "WebBrowser"
            }
            db = container "Database Schema" "Stores configuration data, master data, transaction data releveant to user registration, student info ..." "PostgreSQL" {
                tags "Database"
            }
            vectordb = container "Vector Database" "Stores all the Internal knowledge Base for RAG" "Milvus" {
                tags "Vector Database"
            }            
            api = container "API" "Provides API services for student persona like Authentication, 6e score ..." "FAST API with SQL Alchemy ORM" {
                tags "API"            
                signinController = component "Sign in/Sign up Controller" "New User Registration, Authentication, Authorization returns JWT Token" "Python, oAuth" {
                    tags "API Service"
                }
                scorer = component "6E Framework Scorer" "Calculates 6E Score" "Python" {
                    tags "API Service"
                } 
                documentManager = component "Document Manager" "Writes or Upadtes or Delete the files (BLOB) form" "Python" {
                    tags "API Service"
                }    
                documentVerifier = component "Document Verification" "Verifies Documents ( certificates ) form" "Python" {
                    tags "API Service"
                }  
                careerGuidence = component "Career Builder Engine" "Recomends personalized career paths & Guidance for students based on their current profile and market demand" "Python" {
                    tags "API Service"
                }   
                crud = component "CRUD" "CRUD Operations for other options like Social & Challenges" "Python" {
                    tags "API Service"
                }  
                emailComponent = component "E-mail Component" "Send e-mails to users" "Python" {
                    tags "API Service"
                }   
                notificationComponent = component "Notification Component" "Send notifications to UI" "Python WebSocket" {
                    tags "API Service"
                }                  
              
            }    
            objectStorage = container "Object Storage" "stores all the BLOBS like student documents ( certifications ..)" "s3 or MinIO or Azure Blob Storage" {
                tags "ObjectStorage" 
            }  
            AIService = container "AI Engine" "Build, Evaluate, deploy, Trace AI Applications" "Azure AI Foundry" {
                tags "AI Service" "Used to implement all AI Services"
            } 
            cache = container "Cache DB" "Caches all the API responses" "Redis"  {
                tags "Database" 
            }             
        }

        userStudent -> pramaanik.studentUI "Visits pramaanik.ai using" "https"
        userFaculty -> pramaanik.facultyUI "Uses to mentor cohorts and validate student achievements."
        userInstitute -> pramaanik.instituteUI "Uses to verify records, analyze outcomes, and benchmark employability."
        userIndustry -> pramaanik.inductryUI "Uses to access verified profiles, assess skills, and run targeted hiring initiatives."
        userPolicy -> pramaanik.policyUI "Uses to derive insights, inform policies, and benchmark national skills readiness."
        userAdmin -> pramaanik.adminUI "Uses to configure, manage, and monitor the platform"        

        pramaanik.studentUI -> pramaanik.studentDashboardPage "Delivers to the Student Web browser"
        pramaanik.studentDashboardPage -> pramaanik.API "Makes API calls to" "JSON / HTTPS / WebSocket"      
        userStudent -> pramaanik.studentDashboardPage "Views 6E score, progress, upload documents, carrire guidance ... using"
        pramaanik.API -> pramaanik.db "Reads from and writes to"
        pramaanik.API -> pramaanik.objectStorage "Reads files from and writes to I/O"
        pramaanik.API -> pramaanik.AIService "Makes API calls to AI Applications" "JSON/ HTTPS"    
        pramaanik.API -> pramaanik.cache "Reads from writes to"  
        pramaanik.API -> sendemails "Sends e-mail using" "SMTP" {
            tags "ExternalDependency"
        }            
  
        sendemails -> userStudent "Send e-mails to"         

        pramaanik.studentUI -> idp "Sign-Up or Sign-In using Single Sign On (SSO) [Recieves Token]" {
            tags "ExternalDependency"
        }
        pramaanik.API -> trainingCertificationProvider "Makes API calls Validate & Varify Certifications" "JSON / HTTPS" {
            tags "ExternalDependency"
        }
        pramaanik.AIService -> knowledgeBases "Consumes External Knowledge base from" "JSON / HTTPS"{
            tags "ExternalDependency"
        }    
        pramaanik.AIService -> pramaanik.db "consume student data from"
        pramaanik.AIService -> pramaanik.objectStorage "consume student Documents from"
        pramaanik.AIService -> pramaanik.vectordb "Consume Internal Knowledge base from"
        pramaanik.studentDashboardPage -> pramaanik.api.signinController "Makes API calls to"
        pramaanik.studentDashboardPage -> pramaanik.api.scorer "Makes API calls to"
        pramaanik.studentDashboardPage -> pramaanik.api.documentManager "Makes API calls to"
        pramaanik.studentDashboardPage -> pramaanik.api.careerGuidence "Makes API calls to"        
        pramaanik.studentDashboardPage -> pramaanik.api.crud "Makes API calls to"        
        pramaanik.studentDashboardPage -> pramaanik.api.notificationComponent "Event Listening"
        pramaanik.api.documentManager -> pramaanik.api.documentVerifier "Verify New Documents"
        pramaanik.api.documentVerifier -> trainingCertificationProvider "Makes API calls to"
        pramaanik.api.documentManager -> pramaanik.objectStorage "Reads files from and writes to I/O"
        pramaanik.api.signinController -> pramaanik.db "Reads from and writes to"
        pramaanik.api.careerGuidence -> pramaanik.AIService "Makes API call to"
        pramaanik.api.crud -> pramaanik.db "Reads from and writes to"       
        pramaanik.api.scorer -> pramaanik.db "Reads from and writes to" 
        pramaanik.api.documentVerifier -> pramaanik.db "Reads from and writes to" 
        pramaanik.api.documentManager -> pramaanik.db "Reads from and writes to" 
        pramaanik.api.notificationComponent -> pramaanik.db "Reads from and writes to" 
        pramaanik.api.signinController -> pramaanik.api.emailComponent "Send e-mail notification"
        pramaanik.api.emailComponent -> sendemails "Send e-mails to users"
    }

    views {
        systemContext pramaanik "Diagram1" {
            include *
            title "PRAMAANIK-AI - System Context"
        }

        container pramaanik "Diagram2" {
            title "PRAMAANIK-AI - Containers & Integrations"
            include userStudent    
            include idp
            include trainingCertificationProvider
            include knowledgeBases
            include sendemails
            include pramaanik.studentUI 
            include pramaanik.studentDashboardPage
            include pramaanik.API
            include pramaanik.objectStorage
            include pramaanik.db
            include pramaanik.AIService
            include pramaanik.vectordb
            include pramaanik.cache


        }
        component pramaanik.api "Diagram3" {
            title "PRAMAANIK-AI - Components & Integrations"

            include pramaanik.studentDashboardPage
            include pramaanik.api.signinController
            include pramaanik.api.scorer
            include pramaanik.objectStorage            
            include pramaanik.api.documentManager
            include pramaanik.api.careerGuidence
            include pramaanik.api.documentVerifier
            include pramaanik.api.crud             
            include trainingCertificationProvider
            include pramaanik.db
            include pramaanik.AIService
            include knowledgeBases
            include pramaanik.vectordb
            include pramaanik.api.notificationComponent
            include pramaanik.api.emailComponent
            include sendemails
            
            autolayout tb

        }        

        styles {
            element "Element" {
                background #003153
                color #ffffff
                stroke #0773af
                strokeWidth 7
                shape roundedbox
                width 600
                height 400
                fontSize 32
            }
            element "Person" {
                shape person
            }
            element "Database" {
                shape cylinder
            }
            element "WebBrowser" {
                shape WebBrowser
            }            
            element "Boundary" {
                strokeWidth 5
            }
            relationship "Relationship" {
                thickness 6
                fontSize 45
                width 400
            }

            element "External" {
                background #FFF7ED      
                stroke #C2410C         
                strokeWidth 5
                color #3F1D0F
                shape roundedbox
            }

            relationship "ExternalDependency" {
                color #C2410C
                thickness 6
                dashed true
            }
        }
    }

    configuration {
        scope softwaresystem
    }
}
```