node {
stage "checkout"
def repositoryUrl = "https://github.com/g0t4/jenkins2-course-spring-boot.git/"
git "${repositoryUrl}"

stage "build"
def mvn_version = 'Maven 3.5.3'
def mvn_home = tool "${mvn_version}"
def mvn = "${mvn_home}/bin/mvn"

    dir('spring-boot-samples/spring-boot-sample-atmosphere/') {
    def artifactPath = "target/*.jar"
        
        sh "${mvn} clean package"
        
        stage "archive"
        archiveArtifacts "${artifactPath}"
        
    }
} 
