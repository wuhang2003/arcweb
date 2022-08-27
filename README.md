# **Arcweb**

An svg score generator in arcaea

## Routes

| route     | arg                  | interface            | example                       |
| --------- | -------------------- | -------------------- | ----------------------------- |
| /         | -                    | recently played song | /                             |
| /best     | song and difficulty* | best score           | /best?song=nhelv&difficulty=1 |
| /songlist | -                    | song list            | /songlist                     |

```
*song is for songid in arcaea , can be found in songlist
*difficulty is for short name or full name of difficulties
	 "future" "ftr" "2" are acceptable

**use keyword s="xxx" can specify a user by a secret id , secret id can be generated by /utils/auth.py [see Generate a secret id]
```

## Generate a secret id

First of all , you should set an `auth` environmental variable , which should be the same as the one to be deployed to vercel

Then head to `utils` folder and run

```bash
$ python3 auth.py # or python auth.py
```

input the usercode and it will return a secret id like this:

```
input your id > 000000001
Secret Id : 562f86d6fe0ce87b81ebc281ff826794
Secret Id decrypted : 000000001
```

## Deploy to vercel

Fork this repository and import it from [vercel](https://vercel.com/)

![img](guide/ConfigureProject.png)

Then configure your project:

Set `FRAMEWORK PRESET` to `Other`

Add `Environment Variables`

```
host = "xxxxxx" # for ArcaeaUnlimitedApi
token = "xxxxxx" # for ArcaeaUnlimitedApi
usercode = "xxxxxx" # default query user
auth = "xxxxxx" # a DES key for auth
timezone = "xxxxxx" # [optional] Asia/Shanghai for default
```

Click `Deploy `and wait for building


## Developing Environment

```
Python 3.8.4 (tags/v3.8.4:dfa645a, Jul 13 2020, 16:46:45) [MSC v.1924 64 bit (AMD64)] on win32
Windows 7
```
