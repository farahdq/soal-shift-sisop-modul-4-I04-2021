# soal-shift-sisop-modul-4-I04-2021
## MEMBER 
	Hika Pasya Mustofa		05111942000015
	Farah Dhiah Qorirah		05111942000018
	Nadhif Bhagawanta Hadiprayitno	05111942000029
	
# NO 1 
In a department, there was a new lab admin who had nothing to do, his name was Sin. Sin just became an admin exactly 1 month ago. After a month in that lab he finally met great people, one of them was Sei. Sei and Sin became good friends. Because in the past few months there was a lot of buzz about data breach, they decided to make a file system with a robust encode method technique. The file system is as follows :
a. If a directory starts with “AtoZ_”, then that directory will be encoded.
b. If you rename a directory to have a prefix “AtoZ_”, then the directory will be encoded.
c. When encoded directory is renamed to not have encoded name, then the directory will be decoded 
d. For every encoding of a directory (mkdir or rename) will be recorded in a log file. The format is : /home/[USER]/Downloads/[Directory Name] → /home/[USER]/Downloads/AtoZ_[Directory Name]
e. Encoding method is also applied to all other directories inside the encoded directory.(rekursif)

## MEMBER 
The functions used to encode and decode according to the question request are as follows:


# NO 2
Other than that, Sei proposed to create additional encryption methods to increase the security of their computer data . The following is the additional encryption method designed by Sei
a. If a directory is created starting with “RX_[Nama]”, then that directory and its contents will be encoded with a rename according to problem 1 with an additional ROT13 algorithm (Atbash + ROT13).
b. If a directory is renamed starting with “RX_[Nama]”, then that directory and its contents will be encoded with a rename according to problem 1 with an additional Vigenere Cipher algorithm with “SISOP” as it's key (Case-sensitive, Atbash + Vigenere).
c. If an encoded directory is renamed (Removing the “RX_”), then that folder will become unencoded and it's directory contents will be decoded based on it's real name.
d. Every encoded directory created (mkdir or rename) will be noted to a log file with it's methods (whether it's mkdir or rename).
e. For this encryption method, files in the original directory will be split into smaller, 1024 byte files. While if accessed via the file system designed by Sin and Sei, files will become normal. Example, Suatu_File.txt sized 3 kiloBytes in its original directory will become 3 smaller files::
Suatu_File.txt.0000
Suatu_File.txt.0001
Suatu_File.txt.0002
When accessed via the file system, file will appear as Suatu_File.txt

# NO 3
Because Sin still feels exceptionally empty, he finally adds another feature to their file system.
a. If a directory is created with the prefix "A_is_a_", it will become a special directory.
b. If a directory is renamed with the prefix "A_is_a_", it will become a special directory.
c. If the encrypted directory is renamed by deleting "A_is_a_" at the beginning of the folder name, that directory becomes a normal directory.
d. Special directories are directories that return encryption/encoding to the "AtoZ_" or "RX_" directories but their respective rules still run in the directory within them ("AtoZ_" and "RX_" recursive properties still run in subdirectories).
e. In the special directory, all filenames (excluding extensions) in the fuse will be changed to lowercase (insensitive) and will be given a new extension in the form of a decimal value from the binary value that comes from the difference in character between filenames.

For example, if in the original directory the filename is "FiLe_CoNtoH.txt" then in the fuse it will be "file_contoh.txt.1321". 1321 comes from binary 10100101001.

# NO 4

To make it easier to monitor activities on their filesystem, Sin and Sei created a log system with the following specifications.
a. The system log that will be created is named “SinSeiFS.log” in the user's home directory (/home/[user]/SinSeiFS.log). This system log maintains a list of system call commands that have been executed on the filesystem..
b. Because Sin and Sei like tidiness, the logs that are made will be divided into two levels,INFO and WARNING.
c. For the WARNING level log, it is used to log the rmdir and unlink syscalls.
d. The rest will be recorded at the INFO level.
e. The format for logging is:

[Level]::[dd][mm][yyyy]-[HH]:[MM]:[SS]:[CMD]::[DESC :: DESC]
Level : Level logging, dd : 2 digit date, mm : 2 digit month, yyyy : 4 digit year, HH : 2 digit hour (24 Hour format),MM : 2 digit minute, SS : 2 digit second, CMD : Called System Call, DESC : additional information and parameters
INFO::28052021-10:00:00:CREATE::/test.txt
INFO::28052021-10:01:00:RENAME::/test.txt::/rename.txt





