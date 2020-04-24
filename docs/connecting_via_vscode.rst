=========================
Connecting via VS Code
=========================


Installing SSH extension
========================

1. Open **Visual Studio Code**
2. Press `Ctrl` + `Shift` + `X` to open the extensions panel.
3. In the search box on the left hand side, type `Remote SSH`.
4. This should find lots of extensions, the top one should be **Remote - SSH** and under this it should say **Microsoft**.
5. Click on the extension, and then click **install**. It may ask you to restart **Visual Studio Code**

.. warning:: If you are using windows 10, you may not have an SSH client already.  You will need to install one so that you can connect to the VM.  There are great instructions for installing a client `here <https://www.howtogeek.com/336775/how-to-enable-and-use-windows-10s-built-in-ssh-commands/>`_.

Configuring the SSH Connection
==============================

Now that the SSH extension has been installed, we will need to configure it to connect to our VM.

#. Open visual studio code, and press the **`F1`** key to access the command palette.
#. Click on **Remote-SSH: Connect to Host...**.  If you begin typing this, it should appear in the list.
#. Once you have clicked on this, click on `**Add New SSH Host...*`, and then type

   .. code-block:: bash

      ssh ubuntu@<my_vms_ip>

#. You may be prompted to **Select SSH configuration file to update**.  If so, select ``C:Users\<Name>\.ssh\config``
#. A pop up box should then appear in the bottom right with an option to **Connect**.  Click on **Connect**.
   .. tip:: If the box does not appear follow the instructions for connecting to an existing SSH connection below.

Connecting via SSH
==================

Now that we have configured the SSH connection we will need to connect to it, you may have to do this eveverytime you open VS Code

#. Open VS Code
#. Press the **`F1`** key to access the command palette.
#. Then click on **Remote-SSH: Connect to Host...**.  You should then see the IP address of the machine you want to connect to in the list, click on it.
#. This should open up a new window.  On **Windows** this should have a prompt at the top for you to enter your SSH passphrase. On Linux, your system should prompt for the passphrase.
#. Once it has connected, this window of Visual Studio Code will have access to all the files on the remote machine.

You will probably want access to the **terminal** for the tutorial.  To do this:

#. Click on **Terminal** at the top.
#. Then click on **New Terminal**.


