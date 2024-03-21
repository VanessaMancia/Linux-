# As I prepare to take the RHCSA I will work on practice questions and document them here.

---

- ### Add the following users: Arya, Jon, Rob, and Sansa
- #### ```useradd ``` arya
- ##### We will use the ```useradd``` command for each user

<details>
<summary></summary>

</details>

---
- ### Arya, Sansa, Jon and Rob should be members of a group called Starks
- #### ```groupadd``` Starks
- #### ```tail -1```/etc/group
- #### ```usermod``` Arya -G Starks

---
- ### Jon should also be a member of Snow
- #### ```groupadd``` Snow
- #### ```usermod``` Jon ```-aG``` Snow
- #### ```Id```Jon
---
- ### Set the following password for all users: matrix19
- #### ```echo```"matrix19" | passwd Jon ```-stdin```
---
- ### Force all users to change their password next time they login
- ```passwd``` ```-e``` Arya
- 



  








