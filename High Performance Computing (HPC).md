
**General Information**:  
The cluster consists of 16 compute nodes. All these nodes are part of the BioHPC Cloud, with all the software and tools available in the Cloud also available on the cluster nodes

SSH is a Secure Shell Protocol to send commands to a computer over an unsecured network.


**_Steps to follow:_**

1. **Create account** at https://biohpc.cornell.edu//login_bio.aspx

2. Check if your user password works on biohpc : https://biohpc.cornell.edu//login_bio.aspx 

3. Log in to the **BioHPC** Cluster: you can access with your user in terminal via ssh

   e.g. ssh dg663@cbsurobbins.biohpc.cornell.edu

   - Here you can view the files using ls command and open README file for script using cat "README".
   
   - Look at the README file on that directory it has links to more information on the biohpc site. You can pretty much follow the          example and run a job.
   - The main idea is that you can split jobs into different smaller tasks and have the cluster run them.
   - Other terminal commands like cd or exit or mkdir works here
  

5. **Submit** an Interactive Job: So now you will need to use slurm to submit jobs. There are examples on this directory: /local/workdir/slurm_starter_pack
   
4.1. Submitting jobs using 'sbatch' command:  

- sbatch -N 1 --mem=8000 -p regular /programs/bin/slurm_screen.sh # here node N1, memory 8000 MB on regular partition.
  
OR

- Submit: sbatch --mem=1000 -p regular --wrap="echo 'Hello SLURM\!'"

4.2. Check job status: squeue -u $USER like squeue -u dg663 and output will look like 
        JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
      1729160     short slurm_sc    abc123  R       0:02      1 cbsubscb13

4.3. Copy node from above like (cbsubscb13)

4.4. Check the job status using sacct command: sacct -j 680 #replace 680 with job number assigned in 4.1. above

4.5. SSH into the assigned node: use SSH to access the node where your job is running. Eg. ssh cbsubscb13 #node name from 4.3. step

4.6. Check for Active Screen Sessions: screen -ls and you would see something like: 
There is a screen on : 
99274..cbsubscb13 (Detached)

4.7. Attach to the screen session: screen -r 99274..cbsubscb13

4.8. **Start R** in the Screen session: Once inside the screen session, start R by typing: 
        R
Now you are in R mode and can execute your R commands interactively.

4.9. Detach and Reattach to screen as needed: If you need to leave the screen session but want to keep it running, you can detach by pressing Ctrl + A followed by D.
To reattach later, use the screen -r command as shown above.

4.10. Exit and clean up: Exit using q() or type "exit".



# Move files from local computer to server using scp command (Simplicity, security and pre-installed availability)
- get ip address of your server using: hostname -I
  - eg. I got something like this 128.84.180.45 172.17.0.1
  - from these 16 digits, only 10 digits are IP address so upto .45
- copy directory where your local file is. COPY using **pwd**
- copy dierctory where you wnat to store files. Usually use mkdir and create new folder in the server and then use **pwd** to get the currecnt directory. COPY that.
- Finally use:
- scp from directory username@ipaddress to directory ---- USE THIS IN LOCAL MACHINE OR LOCAL TERMINAL NOT REMOTE SERVER
- eg,. what i used: (can directly drag file after scp to copy file into server below)
- scp /Users/dg663/Desktop/Dinesh/Robbins_Lab/BLUPf90/NMndvi_normal.dat dg663@cbsurobbins.biohpc.cornell.edu:Desktop/dinesh_linux_project
- scp /Users/dg663/Desktop/Dinesh/Robbins_Lab/BLUPf90 dg663@128.84.180.45:/home/dg663/Desktop/dinesh_linux_project
- to copy a whole folder: scp -r /Users/dg663/Desktop/Dinesh/Robbins_Lab/BLUPf90/Practice/Test_data_UGA dg663@cbsurobbins.biohpc.cornell.edu:Desktop/dinesh_linux_project
  - ( r is recursive)
- then the file/folder is moved.
- TO AVOID TYPING PASSWORDS, is used to copy your SSH public key from your local machine to the remote server (cbsurobbins.biohpc.cornell.edu) under the user account dg663. This sets up passwordless SSH login, allowing you to securely access the remote server without entering your password every time.
  - ssh-copy-id dg663@cbsurobbins.biohpc.cornell.edu
- TO SPECIFY THREADS NUMBER i.e. increase parallel computing, bigger data, more threads. eg. OMP_NUM_THREADS=4
- ../blupf90+  or ./blupf90+  : to run blupf90+ where its directory is compared to my current directory. two full stops means two steps back on directory.
- eg. with transferring genotyping file:
   - scp /Users/dg663/Desktop/Dinesh/Robbins_Lab/FFAR/NMSU/Analysis/NMSU\ 2022/Genotype\ files/alfalfa_sample80.vcf dg663@128.84.180.45:/home/dg663/Desktop/Dinesh_folder/Genotyping_22_Alfalfa_NMSU/
   - scp /Users/dg663/FFAR-Alfalfa-NMSU/2022/genotype_data/alfalfa_vcf_gt_dosage_info_merged_sample80.csv dg663@128.84.180.45:/home/dg663/Desktop/Dinesh_folder/Genotyping_22_Alfalfa_NMSU/


