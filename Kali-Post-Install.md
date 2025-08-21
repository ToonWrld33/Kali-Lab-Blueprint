# 🐉 Kali Linux Post-Install Guide

This guide covers **essential steps after installing Kali Linux in VirtualBox**.  
You’ll learn how to:  

- Update & upgrade packages  
- Change passwords (including root)  
- Rename your default user  
- Update your hostname  
- Switch your default shell from Zsh to Bash  

---

## 📜 Table of Contents

- [🔄 Update & Upgrade Kali](#-update--upgrade-kali)  
- [🔑 Change Passwords](#-change-passwords)  
- [👤 Change Username](#-change-username)  
- [💻 Change Hostname](#-change-hostname)  
- [🐚 Change Default Shell](#-change-default-shell)  

---

## 🔄 Update & Upgrade Kali

1. Open terminal and run:  
   ```bash
   sudo apt update
   ```  
   ![Step 1](images/Post-Install/001.png)

2. The system shows how many packages can be upgraded.  
   ![Step 2](images/Post-Install/002.png)

3. Run:  
   ```bash
   sudo apt full-upgrade -y
   ```  
   ![Step 3](images/Post-Install/003.png)

4. Packages begin downloading and upgrading.  
   ![Step 4](images/Post-Install/004.png)

5. Reboot the system:  
   ```bash
   reboot
   ```  
   ![Step 5](images/Post-Install/005.png)

---

## 🔑 Change Passwords

6. Open terminal and type:  
   ```bash
   passwd
   ```  
   ![Step 6](images/Post-Install/006.png)

7. Enter current password → new password → confirm.  
   ![Step 7](images/Post-Install/007.png)

8. Password updated successfully.  
   ![Step 8](images/Post-Install/008.png)

9. Switch to root:  
   ```bash
   sudo su
   ```  
   ![Step 9](images/Post-Install/009.png)

10. As root, set a password with:  
    ```bash
    passwd
    ```  
    ![Step 10](images/Post-Install/010.png)

11. Root password set successfully.  
    ![Step 11](images/Post-Install/011.png)

12. Log out → login screen, sign in as `root`.  
    ![Step 12](images/Post-Install/012.png)

---

## 👤 Change Username

13. Run:  
    ```bash
    usermod -l ToonWrld -d /home/ToonWrld -m kali
    ```  
    ![Step 13](images/Post-Install/013.png)

14. If you get “process currently in use,” kill the session:  
    ```bash
    kill -9 822  
    pkill -u kali  
    usermod -l ToonWrld -d /home/ToonWrld -m kali
    ```  
    ![Step 14](images/Post-Install/014.png)

15. Update the group name:  
    ```bash
    groupmod -n ToonWrld kali
    ```  
    ![Step 15](images/Post-Install/015.png)

16. Log out and log in with the new username.  
    ![Step 16](images/Post-Install/016.png)

---

## 💻 Change Hostname

17. Edit the hostname file:  
    ```bash
    sudo nano /etc/hostname
    ```  
    ![Step 17](images/Post-Install/017.png)

18. Change `kali` → `tutorials`.  
    - Save with **CTRL+O**, exit with **CTRL+X**.  
    ![Step 18](images/Post-Install/018.png)

19. Edit the hosts file:  
    ```bash
    sudo nano /etc/hosts
    ```  
    ![Step 19](images/Post-Install/019.png)

20. Replace `kali` → `tutorials`. Save & exit again.  
    ![Step 20](images/Post-Install/020.png)

21. Reboot the system.  
    ```bash
    reboot
    ```  
    ![Step 21](images/Post-Install/021.png)

22. Confirm hostname:  
    ```bash
    hostname
    ```  
    ![Step 22](images/Post-Install/022.png)

---

## 🐚 Change Default Shell

23. Check current shell:  
    ```bash
    echo $SHELL
    ```  
    ![Step 23](images/Post-Install/023.png)

24. Output should show `/usr/bin/zsh`.  
    ![Step 24](images/Post-Install/024.png)

25. Change to bash:  
    ```bash
    chsh -s /bin/bash
    ```  
    ![Step 25](images/Post-Install/025.png)

26. Reboot again.  
    ![Step 26](images/Post-Install/026.png)

27. Confirm shell changed:  
    ```bash
    echo $SHELL
    ```  
    → Now shows `/bin/bash`.  
    ![Step 27](images/Post-Install/027.png)

---

🎉 Done! Kali is updated, secured, renamed, and customized. Perfect baseline for pentesting labs.
