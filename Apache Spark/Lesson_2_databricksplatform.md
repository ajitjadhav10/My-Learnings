##### Basics of working with dataframes in Apache Spark


How to access DBFS: DBFS is a virtual file system.

- **%fs ls** command is used to see the location of the files in the directory
- %fs is shortform for dbutils module dbutils.fs
- %fs mount displays what is mounted within the dbfs
- **%fs ls file path** or dbutils.fs.ls('file path') displays the files which are present at that location.
- display(dbutils.fs.ls('file path') ) will show the same thing as above, but in a table format
- dbutils.fs.mkdirs("/foobar/") will create a new directory
- dbutils.fs.mkdirs("/foobar/baz.txt","Hello, World!")
- **fs head file_path** allows you to read the file
