1 from datetime import datetime
2 end_time = datetime (2021, 1, 1, 20) # y, m, d, h, min

3 sites_to_block = ['https://verloop.io/', 'https://verloop.io']

4 hosts_path='/etc/hosts'

5 #r"C:\Windows\System32\drivers/etc/hosts"

6 redirect="127.0.0.1"

7 def block_websites():

8 if datetime.now() < end_time:

9

print("Block sites")

with open(hosts_path, 'r+') as hostfile:

10

11

hosts_content = hostfile.read()

12

for site in sites_to_block:

13

if site not in hosts_content:

hostfile.write(redirect + + site + '\n')

14

15

else:

16

17

print('Unblock sites')

with open(hosts_path, r+') as hostfile:

18

lines = hostfile.readlines()

19

hostfile.seek (8)

20

for line in lines:

21

22

23

if not any(site in line for site in sites_to_block): hostfile.write(line) hostfile.truncate()

24

25 if __name.... '__main__':

26

block_websites()
