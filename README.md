# AWSCodeSeries
## AWS CodeCommit
1. HTTPS Git credentials (계정에 권한 할당)
2. CodeCommit에서 repository 생성
3. git clone https://git-codecommit.ap-northeast-2.amazonaws.com/v1/repos/레포지토리명
4. DemoApp 업로드: git remote -v / git add . / git commit -m '메시지' / git push origin master
5. EC2 역할생성: AmazonS3FullAccess, AWSCodeDeployFullAccess, AmazonEC2RoleforAWSCodeDeploy, AmazonSSMManagedInstanceCore
6. CodeDeploy 역할 생성: AmazonS3FullAccess, AWSCodeDeployRole
## AWS CodeBuild 
1. S3 생성
2. CodeBuild 생성
3. Buildsepc 작성하고 디렉토리에 맞춰서 작성
4. CodeBuild에서 빌드 시작
5. S3에서 빌드된 파일 확인
## AWS CodeDeploy 
1. ec2 생성
2. ec2 설정 
```
sudo yum update -y
sudo yum install ruby -y
sudo yum install wget
wget https://aws-codedeploy-ap-northeast-2.s3.ap-northeast-2.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
sudo service codedeploy-agent status
sudo yum install -y tomcat-webapps tomcat-docs-webapp tomcat-admin-webapps
```

```
sudo systemctl start tomcat
sudo systemctl status tomcat
```
3. EC2의 보안에서 IAM 역할 할당
4. CodeDeploy 애플리케이션 생성
5. 배포그룹 생성
6. 배포 생성, S3에서 빌드된 파일의 S3 URI 복사 붙여넣기
7. 배포
## AWS CodePipeline
1. Source
2. Build
3. Deploy

### TroubleShooting
CodeDeploy agent was not able to receive the lifecycle event. Check the CodeDeploy agent logs on your host and make sure the agent is running and can connect to the CodeDeploy server.

```
sudo service codedeploy-agent restart
```