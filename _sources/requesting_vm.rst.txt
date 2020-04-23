=============================
Requesting a VM
=============================

Generating SSH Keys
===================

Using SSH Keys is a more secure and more convienient authentication method than passwords.  This uses a pair of keys; a public key that you can give to someone, or put on a machine you want to access, and a private key that you keep to yourself and never give to anyone.

To create an SSH Key pair, open up a terminal and type the keygen command:

.. code-block:: bash

  ssh-keygen -t rsa

This will bring up a prompt asking you where to save the public-private key pair.

.. code-block:: bash

  Generating public/private rsa key pair.
  Enter file in which to save the key (/home/<user_name>/.ssh/id_rsa): 


Note, the file will have a different path in Windows and MacOS

You can just press _Enter_ here to save them in the default file.  You will then be prompted for a passphrase (a password) for this file.  It is highly encouraged to use a passphrase, not doing so is insecure.

.. code-block:: bash

  Enter passphrase (empty for no passphrase): 


This will then print out some information like below.

.. code-block:: none
  
  Your identification has been saved in /home/<username>/.ssh/id_rsa.
  Your public key has been saved in /home/<username>/.ssh/id_rsa.pub.
  The key fingerprint is:
  SHA256:/TMLeYQjjr0UhxJqJOfbr5gYbvszACQHaLn31nQbm2E <username>@<machine_name>
  The key's randomart image is:
  +---[RSA 3072]----+
  |o..              |
  |o+.              |
  |+.o o .          |
  |.. * . o E .     |
  | .. = + S @ .    |
  |  .. = * B =     |
  |  ..o o + o =    |
  | ..ooo o . o +   |
  | .+o+o..o   .    |
  +----[SHA256]-----+


The part of this pair that you will need for creating the virtual machine is the public key. Unless you changed the default location, you can view it by typing:

.. code-block:: bash

  cat /home/<username>/.ssh/id_rsa.pub

and in windows

.. code-block:: psm1

  type "C:\Users\<Name>\.ssh\id_rsa.pub"


How to get a VM with cwltool in EBI (OpenStack)
===============================================

1. Open [https://cloud-portal.ebi.ac.uk/](https://cloud-portal.ebi.ac.uk/) in the browser (Chrome usually works).
2. Click **Sign On** in the upper right corner. On the page Access the EBI Cloud Portal (with Robby the Robot) click **elixir SSO**
3. Log in using your Elixir account.
4. After successful login you should land on the page **Repository**. You can always come back to it by choosing **Application Repository** from the menu (which looks like three stacked horizontal lines) in the upper left corner.
5. You should see a tile named **CWL VM environment (SHARED)**. If not, then your account needs to be added to the BioExcel Embassy team. If you cannot locate CWL VM environment, contact me (aniewielska@ebi.ac.uk)
6. Click **'CWL VM environment shared'**, which will take you to the deployment wizard page.

7. Click on **Select configuration** and select **CWL BioExcel | @(Embassy ext05 BioExcel) OSTACK** from the drop down list.  If this option is not available, contact ania.
.. Ignore the error next to deployment parameters (some parameters remain unassigned).
8. Click **Next**.
9. Paste your public SSH key in the text field labelled **SSH key**.

See section SSH Keys if you don' have one.

10. Click **Next**.
11. You do not need to enter anything in the fields in this page, so just click **Next**.
12. Click **DEPLOY**.
13. A pop-up box should appear asking you to confirm the deployment.  Click **DEPLOY**.

The deployment process will start. It takes approximatly 10 minutes. There may be an error, but this should be fine. Once it has finished deployment, you will see some text under the heading **ssh_command**.  You can use this to ssh into the machine. Note, that there needs to be a space between ssh and ubuntu, which is missing here.  The ssh command should be of the form ``ssh ubuntu@11.11.111.11`` where the last string of numbers is the IP address of the virtual machine created for you.


Connecting to the Virtual Machine (VM)
======================================


Using SSH in a terminal
-----------------------

Open a terminal (In windows, press the windows key and type `powershell` and the press `enter`) and type:

.. code-block:: bash
		
  ssh ubuntu@<my_vms_ip>


replacing `<my_vms_ip>` with the IP address of your VM.  If you setup the publickey with a passphrase it should prompt you for the passphrase.  You will be prompted for the pass phrase usually once every 24 hours, or after a reboot, which ever occurs first.
