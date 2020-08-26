## Welcome to OpenShift Advanced Application Deployment 
Instructor:   Chád (shod) Darby, cdarby@redhat.com

Dates and Times:  24-28 August, 2020
Monday: 1030 - 1800 (Brazil-Sao Paulo time, GMT-3)
Tuesday through Friday: 1000 - 1800 (Brazil-Sao Paulo time, GMT-3)
Lunch: 1300 - 1400

Course Materials (slides + labs)
** Esta en este repositorio ** 

Communications
BlueJeans Meeting Link: https://bluejeans.com/129763372
Slack: https://join.slack.com/t/red-hat-gpte/shared_invite/zt-ebnmuruf-wfZUV783jhfZy57FICpGHw

Class attendees (Enter your full name and email) - REQUIRED FOR ATTENDANCE:
Chád Darby, cdarby@redhat.com
Rodrigo Canhissare, canhissare@redhat.com
Jose Franco, jose.franco@semperti.com
Marko Aular, markoantonio.aular@semperti.com
João Simões, joao.simoes@scalait.com
Renato Guimarães, renato.guimaraes@la.logicalis.com
Guilherme dos Santos Silva, guilherme.camposo@redhat.com
Alexandre Dos Santos, adossant@redhat.com
Thiago Osório, tosorio@redhat.com
Luiz Gustavo Chiaretto, chiaretto@redhat.com
Jade Luiza Lassery, jadsanto@redhat.com
Priscilla Ordenes, pordenes@redhat.com
Remington Santos, resantos@redhat.com
Andrea Castellanos, ancastel@redhat.com
Alexon Oliveira, alexon@redhat.com
Ezequiel Brizuela - ebrizuel@redhat.com
Santiago Maudet - smaudet@redhat.com
Adriano Luz Rodrigues - adriano.rodrigues@qriar.com
c.desiderio.arana@accenture.com
Marias Viviana Delaluz Ramírez - mdelaluz@redhat.com
Andre Araujo - agaraujo@stefanini.com

======

Structure of Course
Slides in the morning: 1 - 2 hours
Labs in remaining time
Slides: 30%, Labs 70%

Homework Assignment
-  You will complete this on your own time after the class is over
-  You have 4 weeks to turn in homework assignment

Classroom Rules
    1. Be nice - there are no stupid questions. Everyone is at different levels of learning in OpenShift. We all know different things.
    2. Use the "Parking Lot" at the end of this doc for off-topic questions or for things that we couldn't answer during discussion.


OPENSHIFT CLUSTER ENVIRONMENT

OpenShift Web UI: http://console-openshift-console.apps.cluster-d9da.d9da.example.opentlc.com
User: userxxx
Password: r3dh4t1!

See Student Assignment Sheet for your user id
https://docs.google.com/spreadsheets/d/1WVnzmicSFCEmR_TyXqmrlWbpYaxzgMcrDWN2hQ28Uro/edit?usp=sharing

1. Order a Student VM  (you will use this to access the OCP cluster)
   - Linux VM ... has all of the classrooms tools preinstalled: oc, jq, skopeo, podman

Cluster: Available Monday - Friday, (available 24 hours a day)
              - Will expire on Friday at 8pm (Brazil-Sao Paulo time, GMT-3)

====

OPENSHIFT RESOURCES, DOCUMENTATION AND TIPS

This class is inspired by the book
DevOps with OpenShift,  by Stefano Picozzi et al
https://www.amazon.com/DevOps-OpenShift-Cloud-Deployments-Made-ebook/dp/B073V7JC8Z/

OpenShift 4 Docs: https://docs.openshift.com/container-platform/4.4/welcome/index.html
Note: If you can't find something in the OpenShift 4 docs, try the OpenShift 3 docs. Much is the same when it comes to apps and workloads.

Cheat Sheets and Reference Cards (bash, git, oc, vim, Docker, Jenkins, etc.)
https://github.com/redhat-gpte-devopsautomation/reference

*Be prepared for struggle, it's the best way to learn: https://medium.freecodecamp.org/why-you-learn-the-most-when-you-feel-like-youre-struggling-as-a-developer-7513327c8ee4

I recommend you use my links below for the lab guides. Sometimes we make fixes during the week. If you are using the LMS to access your lab guide, you will not get those fixes real-tme.
 
 At the end of the week,  I will give a zip file that has all course materials: slides and labs
 
 Slides:  take break at the top each of hour (15 mins)
 
=============
 
Day 1 - Introductions & Controllers
Module 1: Intro
    http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/01_Course_Intro/AllSlides.html

Module 2: 12 Factor Applications
    http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/02_12_Factor_Applications/AllSlides.html

Module 3: Controllers
     http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/03_Controllers/AllSlides.html

    Lab: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/03_Controllers/03_1_Controllers_Lab.html
    Lab Solution: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/03_Controllers/03_1_Controllers_Solution_Lab.html


 
oc set env is easiest way to set environment variables
-but, if you love jsonpatch...
oc patch dc/green  -p '{"spec": {"template": {"spec": {"containers": [{"name": "green", "env": [{"name": "SELECTOR", "value": "pets"}]}]}}}}'

============= 

Day 2 - Operators & CI/CD Tools
Module 4: Operators
Slides:     http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/04_Operators/AllSlides.html

Operators Lab: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/04_Operators/04_1_Operators_Lab.html
Operators Lab Solution:http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/04_Operators/04_1_Operators_Solution_Lab.html

-----
[Ezekiel] If you have issues with the password setting in the quay.io account, like Anyone with redhat credentials linked. Just create a robot account and use that credentials to login in podman login step.
-----

OpenShift Docs - Operators
https://docs.openshift.com/container-platform/4.4/operators/olm-what-operators-are.html

Learn More about Operators (3 min video)
https://www.openshift.com/learn/topics/operators

Video: Kubernetes Operators Explained  (10 min video, really good!)
https://www.youtube.com/watch?v=i9V4oCa5f9I

Red Hat OpenShift - YouTube Playlist - Operators
https://www.youtube.com/playlist?list=PLaR6Rq6Z4Iqfwgl2JIqhR3_mJgT8KLdjd

User Quota Operator: https://github.com/redhat-gpte-devopsautomation/userquota-operator 
Project Deletion Operator: https://github.com/redhat-gpte-devopsautomation/project-cleanup-operator
Namespace configuration Operator: https://github.com/redhat-cop/namespace-configuration-operator 

Module 5: CI/CD tools

Slides: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/05_CICD_Tools/AllSlides.html

Lab: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/05_CICD_Tools/05_1_CICD_Tools_Lab.html
Lab Solution: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/05_CICD_Tools/05_1_CICD_Tools_Solution_Lab.html

SonarQube Image Source: https://github.com/wkulhanek/docker-openshift-sonarqube
Gogs Image Source: https://github.com/wkulhanek/docker-openshift-gogs
(Gitea Image Source): https://github.com/wkulhanek/docker-openshift-gitea

Blog Post on using Persistent Volumes in Jenkins Agent Pod:
    https://blog.openshift.com/decrease-maven-build-times-openshift-pipelines-using-persistent-volume-claim/
    One correction: Mount the volume in /home/jenkins/.m2/repository, NOT /home/jenkins/.m2 (otherwise you overwrite the stock settings.xml - we don't notice it because we always use a -s settings.xml from the repo anyway....)
    Realize that in OCP4 (on AWS) we only have RWO volumes - so parallel builds won't work with a volume...

oc get templates -n openshift | grep <search>
oc get template <template-name> -n openshift -o yaml > template
oc get crd.yaml
 
How to find something in OpenShift resources (e.g. emptyDir):
    for r in $(oc api-resources | cut -f1 -d" ") ; do echo $r ; oc explain $r --recursive=true | grep emptyDir ; done

=============

Day 3 - Building Applications
Module 6: Building Applications

Slides: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/06_Building_Applications/AllSlides.html

Lab: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/06_Building_Applications/06_1_Building_Applications_Lab.html
Lab Solution: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/06_Building_Applications/06_1_Building_Applications_Solution_Lab.html


To clarify seeing the path in the deployment config for the check in slide  (while (rc.spec.replicas != rc.status.readyReplicas) :
$ oc get rc ola-1 -o json|jq '.|{Required: .spec.replicas, Ready: .status.readyReplicas}'
{
  "Required": 1,
  "Ready": 1
}

=============

Day 4 - Pipelines
Module 7: Pipelines

Slides: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/07_Pipelines/AllSlides.html
 
Lab: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/07_Pipelines/07_1_Pipelines_Lab.html
Lab Solution: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/07_Pipelines/07_1_Pipelines_Solution_Lab.html
  

Jenkins 
Using Build Strategies
 https://docs.openshift.com/container-platform/4.4/builds/build-strategies.html
 
White Paper on CICD with OCP and Jenkins (with the tagging strategy we use)
    https://access.redhat.com/documentation/en-us/reference_architectures/2017/html/application_cicd_on_openshift_container_platform_with_jenkins/
  
Jenkins in a Nutshell: https://dzone.com/articles/jenkins-in-a-nutshell
Jenkins using PVC: https://blog.openshift.com/decrease-maven-build-times-openshift-pipelines-using-persistent-volume-claim/ (mount at .m2/repository, NOT .m2)
Jenkins Day 2: https://access.redhat.com/articles/3714291
 
Jenkins Pipeline examples: https://github.com/jenkinsci/pipeline-examples
 
OpenShift integration with external Jenkins:
    http://uncontained.io/articles/external-jenkins-integration/
    
OpenShift Plugin for Jenkins:
    https://github.com/openshift/jenkins-client-plugin
    
Running Jenkins Builds in Containers:
    https://itnext.io/running-jenkins-builds-in-containers-458e90ff2a7b

Tekton
Community Website
https://tekton.dev/

OpenShift Pipelines (Tekton)  - tech preview
https://www.openshift.com/learn/topics/pipelines

Understanding OpenShift Pipelines - official docs
https://docs.openshift.com/container-platform/4.4/pipelines/understanding-openshift-pipelines.html

Creating Pipelines with OpenShift 4.4’s new Pipeline Builder and Tekton Pipelines
https://developers.redhat.com/blog/2020/04/30/creating-pipelines-with-openshift-4-4s-new-pipeline-builder-and-tekton-pipelines/

---

Trick to make starting pipelines faster (don't look for already running agent pods - there are never any anyway):
oc set env dc/jenkins JENKINS_JAVA_OVERRIDES="-Dhudson.slaves.NodeProvisioner.initialDelay=0 -Dhudson.slaves.NodeProvisioner.MARGIN=50 -Dhudson.slaves.NodeProvisioner.MARGIN0=0.85 -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=300"
 
Sonarqube Analysis Parameters
https://docs.sonarqube.org/latest/analysis/analysis-parameters/
 
Declaritive vs Groovy (Scripted)
https://jenkins.io/doc/book/pipeline/syntax/#compare

UBI & Podman: https://developers.redhat.com/blog/2019/12/09/building-freely-distributed-containers-with-podman-and-red-hat-ubi/

Build Defaults (oc edit bc tasks -n $GUID-tasks-dev)
...
  resources:
    limits:
      memory: 2Gi
    requests:
      memory: 2Gi
...


Homework
Homework assignment: http://ocp-24aug2020-latam.apps.shared-dev4.dev4.openshift.opentlc.com/08_Assignment/08_1_Assignment_Lab.html
  
Please Submit the Survey before you leave today!!!

HOMEWORK IS AN INDIVIDUAL ASSIGNMENT
 
 
OpenShift Pipelines based on Tekton:
    Tekton Overview (Internal Only): https://docs.google.com/presentation/d/1E6FChdbIrMHlynF-yvEMrTiAnR8rwMdvebBxPgdcmrE/edit?usp=gmail
    OpenShift Pipelines Documentation: https://openshift.github.io/pipelines-docs
    OpenShift Pipelines Tutorial: https://github.com/openshift/pipelines-tutorial/
    OpenShift Pipelines Examples: https://github.com/siamaksade/openshift-pipelines-examples
    Tekton Pipelines Documentation: https://github.com/tektoncd/pipeline/tree/master/docs
    Download Tekton CLI: https://github.com/tektoncd/cli#getting-started
    
    OpenShift Pipelines Demo: https://youtu.be/0Nzg-qI2KH0
    What's new in OCP 4.4: https://www.youtube.com/watch?v=CDbu1id1FVI
    Building Images with S2I and Tekton: https://www.youtube.com/watch?v=VblUusADGuQ&authuser=0
    What is Tekton: https://www.youtube.com/watch?v=TWxKD9dLpmk&authuser=0
    Mario's Adventures in Tekton Land: https://www.youtube.com/watch?v=LdXXtDYxD-0&authuser=0
    How to build Cloud Native CI/CD Pipelines with Tekton: https://www.youtube.com/watch?v=-ji5Z0qJmJs&authuser=0
    Plumbing Kubernetes Builds with Tekton: https://www.youtube.com/watch?v=q5P2V_YShjA&authuser=0
    
    Check out different example pipelines for jenkins and tekton: https://github.com/redhat-cop/container-pipelines
    
    K8s troubleshooting guide with excellent diagram to help the workflow downloadable as a PDF: https://learnk8s.io/troubleshooting-deployments

Troubleshooting Kubernetes Deployments
https://learnk8s.io/troubleshooting-deployments

Script to export all projects to files

For OCP4 do (export is deprecated)

projects=$(oc get projects --output=jsonpath={.items..metadata.name})
for project in $projects; do
    echo "exporting project $project"
    oc get --export deploymentconfigs,routes,svc,pvc,buildconfigs,secrets,configmap -n $project -o yaml > $project.yaml
done

To copy everything into a directory of choice:
rsync -azv <username>-redhat.com@bastion.<GUID>.example.opentlc.com:* <directory>


---

Links
https://docs.openshift.com/container-platform/4.4/nodes/containers/nodes-containers-health.html
https://www.mankier.com/1/oc-set-probe

Free eBook: O’Reilly: Kubernetes patterns for designing cloud-native apps
https://www.redhat.com/en/resources/oreilly-kubernetes-patterns-cloud-native-apps


Recommended Courses:
    Red Hat Container Management And Image Builds https://learning.redhat.com/enrol/index.php?id=1857
    Red Hat OpenShift Container Platform 4 Installation https://learning.redhat.com/course/view.php?id=1806
    Red Hat OpenShift Container Platform 4 Resources and Tools https://learning.redhat.com/course/view.php?id=1825
    Red Hat OpenShift Container Platform 4 Configuration https://learning.redhat.com/enrol/index.php?id=1798
    

Parking Lot
https://www.openshift.com/resources/ebooks/devops-with-openshift/ (Free Download)

1. SatefulSets lab - scaling down pods, delete unused pvcs, scale up ... and mongodb fails. is this mongdb specific or general stateful set / pvc issue?






