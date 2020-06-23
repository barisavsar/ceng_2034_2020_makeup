# ceng_2034_2020_makeup


1) Create a new child process with syscall and print its PID. (5 pts)
2) Multi Threading:
Child process should do the following:
● Download the files via the given URL list. Should use multi threading for
retrieving the files. Create n threads if there are n different elements in the url
(10pts)
● url =
["http://wiki.netseclab.mu.edu.tr/images/thumb/f/f7/MSKU-BlockchainResearc
hGroup.jpeg/300px-MSKU-BlockchainResearchGroup.jpeg",
"https://upload.wikimedia.org/wikipedia/tr/9/98/Mu%C4%9Fla_S%C4%B1tk%
C4%B1_Ko%C3%A7man_%C3%9Cniversitesi_logo.png",
"https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Hawai%27i.jpg/
1024px-Hawai%27i.jpg",
"http://wiki.netseclab.mu.edu.tr/images/thumb/f/f7/MSKU-BlockchainResearch
Group.jpeg/300px-MSKU-BlockchainResearchGroup.jpeg",
"https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Hawai%27i.jpg/1024pxHawai%27i.jpg"]
def download_file(url, file_name=None):
 r = requests.get(url, allow_redirects=True)
file = file_name if file_name else str(uuid.uuid4())
open(file, 'wb').write(r.content)
● Child process should check its status; that means if it understands that it is
orphan, it should then remove the downloaded files at the system and then
exit (10pts).
3) Multiprocessing (40 pts Total)
● Check the system and learn the number of CPU cores. Create n processes if
there are n cores. (10 pts)
● Use processes for the correct task!
● Control duplicate files within the downloaded files of your python code. You
should do it by using multi processing techniques. (Hint: you can use hashlib
-md5/sha256- in python to check file checksum) (10 pts)
● The main process should check the other created processes and if takes
more than 30 seconds, kill those processes (by sending signal from the main
process) (10 pts)
● The main process should check If the other processes didn't end successfully,
then it should try again that process's job. (10 pts)
4) Think about the previous questions. Your script should:
a. Check available memory of the system. (5 pts)
b. Estimate what should be the minimum required memory. (5 pts)
c. Include the routine that will wait until the system frees that memory. (5 pts).
d. Take a movie file (> 1GB) in your disk and try to hash it. How can you handle
when hashing files that don't fit in the memory? 
