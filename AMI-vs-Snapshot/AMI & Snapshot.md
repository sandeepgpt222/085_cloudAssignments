**What is the difference between AMI & snapshot?**

**AMI:**  An AMI is a template that contains the software configuration (operating system, application server, and applications) 
required to launch your instance i.e to create a virtusl machine. In layman's we can say that it's an iso image file of an os which
is used to install the operating system in our computers. Many options of AMI is already provided by aws but we can create a virtual
machine using our own AMI if need be, thanks to Amazon's amazing user-friendly UI and services.
  When we create a custom AMI from an instance we actually save a copy of the os,softwares installed in that os and last but not the 
least we also save a copy of the entire volume associated with that instance so that at a later stage we can get the same instance with 
same configurations, softwares and all the files whenever/if we need.

**Snapshot:** Snapshot means taking a backup of any volume/EBS (elastic block store). Amazon EBS gives us the ability to take a snapshot 
or backup of our volume which may or may be a attached to an  instance. This snapshot can then be used to create a new volume and the volume 
thus created gives us an exact replica of the volume to which the snapshot belongs. 
  When we create a snapshot AWS writes a copy of the data in the volume to Amazon S3, where it is stored redundantly in multiple 
Availability Zones. It is noteworthy that Any changes made in the actual volume after creation of snapshot will not automatically reflect
in the snapshot, Thus we have to update the snapshot if those files are important to us.

The major difference between creating a custom **AMI** and a **Snapshot** is:
  1. AMI is acopy of operating system plus the volume associated with that instance. 
     Snapshot is a backup of volume only.
  2. AMI cannot have a backup of any other volume which is not associated with the instance
     Snapshot can be created of any volume and volumes dont necessarily need to be associated with an instance.
  3. AMI is automatically registered by aws. Snapshot needs no registration.
  4. During the AMI-creation process, Amazon EC2 creates snapshots of our instance's root volume and any other EBS volumes attached to 
     our instance.
     Snapshot cretion has no such underlying task.
