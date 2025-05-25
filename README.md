# Operation-Shadow-Trace

Blog 1:

Was able to follow the Kalpit Lal Rama chain to the reddit post https://www.reddit.com/user/Virtual-Copy-637/comments/1fuyetj/comment/lq305zv/?context=3 but alas, could not decipher these numbers.

Blog 2:

Challenge 1:
Grafana Exploit downloaded from exploitdb.com (https://www.exploit-db.com/exploits/50581) which when run, gives access to read the files. Then read the file located in /tmp (/tmp/flag) which gave - "PClub{Easy LFI}, now onto the next one! Next challenge - 13.235.21.137:4657 and 13.235.21.137:4729". (Also before this I was just trying to brute force the crap out of the login page :P)

Flag 1: PClub{Easy LFI}

Challenge 2:
nc 13.235.21.137 4657 connected to the remote terminal. Clearly the file file_chal.c implies that the flag ws located in ~/root/flag but the access was denied. Then I listed the process IDs and then tried to read them but to no avail. At last, using cat <&3 (3 was the PID of the file_chal binary) the flag PClub{4lw4ys_cl05e_y0ur_fil3s} was obtained.

Flag 2: PClub{4lw4ys_cl05e_y0ur_fil3s}

Challenge 3:

Found the files .swo and .swp but was unable to read them due to permissions. Then listed all the swap files and found /tmp/flag but the file was empty so no point in reading that. Since I could run vim, I used that to access a sudo shell, then read the flag. 

Flag 3: PClub{y0u_ar3_in_7he_sudoers_file_1nc1d3nt_will_n0t_be_rep0r7ed}
