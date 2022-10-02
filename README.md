<img src="./buddha.jpg" alt="drawing" width="100"/>

# file-wait

Lightweight file/folder sensor exits after preset delay.

### What is file-wait?

I wrote this as a simpler solution for triggering pipelines in Argo (Kubernetes ETL orchestration framework).

file-wait will wait indefinetely until it recieves an initial file or folder. It will then exit after a preset number of seconds (60 by default). If another file or folder arrives it will wait again. This is great when you are waiting for a set of files that are arriving via scp/rsync/mount or similar. You might know they will all arrive within at most a few minutes of each other. You want to be able to execute another step once the files / folders arrive.

### How to use

To run:
`cargo run` or `cargo build --release`, then `./file-wait`
<br/>

### Environment variables

**REQUEST_SENSOR_PATH**="/Users/me/files-to-watch"  
Folder to watch for new files/folders.

**FILE_SENSOR_DELAY**=200
Time to wait in seconds after arrival of a file / folder before quitting with zero exit code.
