================
Accessing the VM
================

#. In the portal in the details of your Deployment locate the Outputs section (see the last screenshot in previous section). You should find there ssh_command with a value similar to ssh ubuntu@45.86.170.4 (IP might be different).
#. Run that command from your Terminal (or Git Bash in Windows). If you have secured your key with a passphrase, you will be asked for it. Please, provide it.

   .. image:: images/image9.png
      :width: 600
   
#. If you managed to log in to the VM successfully, you will see sth like that:

   .. image:: images/image7.png
      :width: 600




Validate the VM works
=====================

Now you will only check, if CWL is properly installed in the VM.

1. In the terminal of you VM type: cd workflow
2. And then run the test workflow using cwltool, by running a command: ``cwltool hashsplitter-workflow.cwl --input resources/test.txt``
3. You should see something like this:

   .. image:: images/image13.png
      :width: 600
	      
4. Disconnect from the VM by hitting ``CTRL-D``


   
