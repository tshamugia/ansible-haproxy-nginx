Ansible Practical Test
Due May 18, 2024 11:59 PM
Instructions

Objective: Configure a web server using Ansible. 

Task 1: შევქმნათ ორი ვირტუალური მანქანა ვაგრანტის დახმარებით

![Vagrantfile](https://github.com/tshamugia/ansible-haproxy-nginx/assets/93130494/eb61c5e8-30d8-4794-9bbe-98b5c8a29044)

Task 2: Set Up Inventory and Configuration

1.	Inventory File:
•	შევქმნათ inventory ფაილი სახელად [Hosts]  შემდეგი group-ებით და host-ებით:

    [web] -  group with web1 and web2
  	[lb]  -  group with lb1
  	
![Inventory File](https://github.com/tshamugia/ansible-haproxy-nginx/assets/93130494/f6a85c60-2b82-43a8-bb34-def58f1b1230)

Task 3.	Configuration File:
   
•	შევქმნათ ansible.cfg ფაილი იმავე დირექტორიაში სადაც inventory ფაილი იქნება განთავსებული.

•	მიუთითეთ inventory file path და გათიშეთ host key checking-ი.

![ansible confi](https://github.com/tshamugia/ansible-haproxy-nginx/assets/93130494/68675025-d6e8-43e8-a785-fba31ebfc579)

Task 4: Create a Playbook to Configure the Web Servers
1.	Playbook:
   
•	შექმენით playbook-ი სახელად webserver.yml  ვებსერვერის კონფიგურაციისთვის (web1 and web2).
3.	Tasks:
   
•	დააყენეთ nginx-ის latest ვერსია.

•	დარწმუნდით რომ nginx-ის სერვისი არის ჩართული .

•	გადაიტანეთი შეცვლილი HTML file-ი document root დირექტორიაში (/var/www/html/index.html).

4.	Custom HTML File:
   
•	დავალებასთან ერთად არის ატვირთული HTML ფაილები სახელად Server 1 , Server 2.

![webservers tasks](https://github.com/tshamugia/ansible-haproxy-nginx/assets/93130494/d02ccf96-3bdf-4e20-933e-e0011ce8f9cc)

Task 5: Create a Playbook to Configure the Load Balancer 
1.	Playbook:
   
•	შევქმნათ playbook-ი სახელად Loadbalancer.yml   load balancer-ის კონფიგურაციისთვის .

Tasks:

•	Install the latest version of Haproxy.

•	Ensure the Haproxy service is enabled and started.

•	Configure Haproxy to load balance traffic between web1 and web2.


3. HAProxy Configuration:
   
•	Create a Haproxy.cfg file

![Loadbalancer tasks](https://github.com/tshamugia/ansible-haproxy-nginx/assets/93130494/ff5378d9-277a-4bcd-b488-e19f91691339)

Task 6: Create a Main Playbook to Apply All Configurations

1.	Playbook:
   
•	შექმენით main playbook-ი სახელად main.yml 

3.	Structure:
   
•	The main.yml playbook უნდა უშვებდეს webserver.yml  web host ჯგუფით ხოლო loadbalancer.yml -ი lb host ჯგუფით.

![folder structure and main playbook](https://github.com/tshamugia/ansible-haproxy-nginx/assets/93130494/6511d42d-086f-43aa-8bcb-197d50d229ac)

Extra +5 ქულა
node-ებზე შექმენით მომხმარებელი devops
devops მომხმარებელი იყოს sudo-ერი
მომხარებელ devops-ში ჩაამატე ssh-public key-ები
1. ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDG2EOjm9KrJIkJr09eQyQZW5ANPcGnqMRBEHxyDZ3ti1fxV55sgJr9SE5oEUe5ltuVPPHNcPkKzNsa2f6QmDtzgtsjP7jDx60o0J/Tnpxr7ku3uR1WcwflH+v4byrdrZVtyIvhYyhVKM5HKYkiujc6FqmSyeMiA5inZxLeCT01CWE0KzoxoGtx6PiXMeNO2QwgvnoBmRAfFjtCEDlOwQr4U4nB/83zYGqyB6fsc38E+hPJ9f/Ox1COoRw5dEmzUQr339qtl2aIpEFWIDuPnhYTehQbS3/WSCv1cuN60SzJMGRrWp1poDgwqTNeKg5CblC96m4Sy23MgA52oNZWdsQ3 user1@test
2. ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCn1xFHHS43FZLaAA2nvorPXtuElYshTXBfaPHSorMEGt57Knh7wA9XeVBVyePOEa5pfF6Jf2ADYOd1c3Wb6czUljDAs6qWSikLNsh4hJMzGoemTOywqCSCzp+0+Be/MiVjxrdEGKc61RU8jl8GURTTtTT3c7j11EPTMWsv40rUGXsKTJGeo4ZMy3bec7Ha3b4C1zCY6/GK6tOFqDL7tSkxYaMNGQMgvb8xsbEGd3SSGMbS4XWxLOw1IBvzoJ4xW+0VQCtwZx6fN1BILnwxkMPsBfFjjpwnTCu39KBGH+ruj46yiEfNVeQXZVqyyZ/+qzlL3jfl1geFJI2zAp78b5/d user2@test
public_key-ები: დაშიფრული ansible-vault
შესაძლებელი უნდა იყოს key-ების ამოშლა საჭიროების შემთხვევაში


![ssh user tasks](https://github.com/tshamugia/ansible-haproxy-nginx/assets/93130494/173730b2-a605-4d2b-8028-b8f96ba3d2f2)
