# s3syncer
---

**s3syncer** is a gradle plugin which can help your gradle build script to upload local files to s3 and download s3 files. 

<br/>
# Usage
---
## Import plugin
```gradle
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'cn.gridx:s3syncer:1.0-RELEASE'
    }
}
```

<br/>
## Define your task
```gradle
apply plugin: 'cn.gridx.plugins.s3sync.S3SyncTask'

task deployToS3(type: com.gridx.gradle.plugins.s3.S3SyncTask) {
    setAccessKey "<Your Access Key>"
    setSecreteKey "<Your Secrete Key>"
    addLocation "<local file path>", "<s3 bucket name>", "<s3 object key>"
    // ...  you can add more files to upload to s3 by using `addLocation` multiple times
}
```

<br/>
## calling
```gradle
gradle deployToS3
```

