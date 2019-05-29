## aws-backup-cf

A CloudFormation template sample to build AWS Backup(BackupPlan and BackupSelection) just for reference

* aws-backup.yaml
* sample-params.json

#### Sample Parameters 

```
BackupPlanName: daily-backup-sample
BackupSelectionName: daily-backup
Team: appteam:test
Email: team-email@domain.com
## BackupOnceDaily, BackupTwiceDaily, BackupThriceDaily and BackupFourTimesDaily
BackupPolicy: BackupTwiceDaily
BackupDefaultRole: arn:aws:iam::<account>:role/service-role/AWSBackupDefaultServiceRole
DeleteAfterDays: 30
```

#### Test the template

```
$ aws cloudformation create-stack --stack-name <stack name> --template-body file://aws-backup.yaml --parameters=file://sample-params.json 
```


NOTE:

* This template does not include the creation of the BackupVault, It will use the Default BackupVault 

* Add the tag "Backup: daily-backup" to your resources so the AWS Backup can identify the target resource it needs to backup

* Please check here for the supported AWS service https://aws.amazon.com/backup/features

