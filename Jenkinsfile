def version = params?.version

branches {
    snapshotBranch = 'master'
}

intergration {
    snapshot {
        maven {
            goals = 'clean install'
            mavenHome = '/opt/runtime/apache-maven-3.3.9'
            mavenArgs = ['-P jenkins-build -Dorg=fsplatform_snapshot']
        }
        
        dockyard {
            stageName = 'push release image to dockyard'
            tags = version
            buildImage = true
            dockerFile = './ecs/Dockerfile'
        }
    }
}
