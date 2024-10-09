# Module 2: Pondering Paths
## 1. The root

**Task:** Understanding `root( / )` as a part of file structures

**Process:** Finding the flag using the absoulte path `/pwn` , from the root 


**Code:**
```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{k4xj8LxSaP_0TJAbAxpfKfI_d33.dhzN5QDLxYTN0czW}
```
</br>

**Flag:** `pwn.college{k4xj8LxSaP_0TJAbAxpfKfI_d33.dhzN5QDLxYTN0czW}`
</br>
</br>

## 2. Program and absolute paths

**Task:** Using the absolute path by stacking directories

**Process:** Similar to the first task, using an absolute path again. "run" lives in the `/challenge` directory so, we use `/challenge/run` as the absolute path to access the flag


**Code:**
```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{8bHY82DYC9TPthhrySAnG5s77I5.dVDN1QDLxYTN0czW}
```

**Flag:** `pwn.college{8bHY82DYC9TPthhrySAnG5s77I5.dVDN1QDLxYTN0czW}`
</br>
</br>

## 3. Position thy self

**Task:** Understanding `cd` command.

**Process:** Changind directory using `cd` to the one mentioned in the task. then running `/challenge/run` to get the flag.

**Code:**
```bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/share/doc
hacker@paths~position-thy-self:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{oJeSije8_k3a4eIH6y7Yi_0S1mF.dZDN1QDLxYTN0czW}
hacker@paths~position-thy-self:/usr/share/doc$
```

**Flag:** `pwn.college{oJeSije8_k3a4eIH6y7Yi_0S1mF.dZDN1QDLxYTN0czW}`
</br>
## 4. Position elsewhere

**Task:** Similar to task 2

**Process:** Similar to task 2

**Code:**
```bash
hacker@paths~position-elsewhere:/$ /challenge/run
Incorrect...
You are not currently in the /home directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:/$ cd /home
hacker@paths~position-elsewhere:/home$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8XGoWKsJVafRz-3JjYfxTf1HakG.ddDN1QDLxYTN0czW}
hacker@paths~position-elsewhere:/home$
```

**Flag:** `pwn.college{8XGoWKsJVafRz-3JjYfxTf1HakG.ddDN1QDLxYTN0czW}`
</br>
## 5. Position yet elsewhere

**Task:** Similar to task 4

**Process:** Similar to task 4

**Code:**
```bash
Connected!
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /proc/66 directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /proc/66
hacker@paths~position-yet-elsewhere:/proc/66$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{om4l3HViybDiN6BP3bkQ3xF5b2O.dhDN1QDLxYTN0czW}
hacker@paths~position-yet-elsewhere:/proc/66$
```

**Flag:** `pwn.college{om4l3HViybDiN6BP3bkQ3xF5b2O.dhDN1QDLxYTN0czW}`
</br>
## implicit relative paths, from /

**Task:** Understanding current working directory `cwd` and using `./`

**Process:** Using `./` instead of mentioning the entire path.</br> 
`pwd` displays the present working directory 

```bash
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{AdZLiBK77VTqmGgLNunYODvde8N.dlDN1QDLxYTN0czW}
hacker@paths~implicit-relative-paths-from-:/$
```

**Flag:** `pwn.college{AdZLiBK77VTqmGgLNunYODvde8N.dlDN1QDLxYTN0czW}`
</br>
## explicit relative paths, from /

**Task:** Similar to task 6 using `./`

**Process:** Similar to task 6

**Code:**
```bash
Connected!
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{4LDoH6zYyofdOeQiKNRJrYmxPDy.dBTN1QDLxYTN0czW}
hacker@paths~explicit-relative-paths-from-:/$
```

**Flag:** `pwn.college{4LDoH6zYyofdOeQiKNRJrYmxPDy.dBTN1QDLxYTN0czW}`
</br>
## implicit relative paths

**Task:** further understanding of implicit paths.

**Process:** While in the `/challenge` directory, </br>
             We cant use `run` directly as it would be a command and not a directory. </br>
             We use an implicit relative path `./run` which directs us to the flag.

**Code:**
```bash
Connected!
hacker@paths~implicit-relative-path:~$ /challenge/run
Incorrect...
You are not currently in the /challenge directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ run
ssh-entrypoint: run: command not found
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{MEHbRCcdsBAcGQ6dcUkjrsWHr6k.dFTN1QDLxYTN0czW}
hacker@paths~implicit-relative-path:/challenge$

```

**Flag:** `pwn.college{MEHbRCcdsBAcGQ6dcUkjrsWHr6k.dFTN1QDLxYTN0czW}`
</br>
## home sweet home

**Task 9:** Using `~` and moving between directories

**Process:** `~` : Signifies `/home/hacker`</br>
            `~/` : Signifies `/home/hacker/` followed by the directory you mention
            as said in the the task- we need to run `/challenge/run` with a 3 character argument which is an absolute path.
            for example: `~/a`

**Code:**
```bash
Connected!
hacker@paths~home-sweet-home:~$ /challenge/run
You must provide an argument to /challenge/run when you invoke it!
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{cuQoZitptLILhQtc795v6OObF6e.dNzM4QDLxYTN0czW}
hacker@paths~home-sweet-home:~$ 
```

**Flag:** `pwn.college{cuQoZitptLILhQtc795v6OObF6e.dNzM4QDLxYTN0czW}`
