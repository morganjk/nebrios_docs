Parent Child Processes
======================

What if you want to spawn a new PID from an existing PID? For example, you have a process in motion that orders new food items when low, but now you want to launch the freezer cleaning process and not have it effect your order process. In this case it's best launch a whole new child process. 

:: 
    
    new_child.clean_freezer == True

The child process is now in the ether, if you will. It will go on it's merry way and accomplish what its designed to. It acts like any other process at this point. The parent process can disappear all together without effecting spawned processes. 

You also have the ability to communicate with that child process. Maybe you want to know the status of it? 

::
    ...

    listens_to = ['child.clean_freezer']

    ...
    
    def check(self):
        return child.clean_freezer == "Done"

    def action(self):
        # notify boss: ok to book a restaurant tour

In the same way, children can monitor their parents:
    
:: 

    listens_to = ['parent.example']

.. todo:: Write about children


Full reference for the Parent/Child tools:

* :doc:`../library/parent`
* :doc:`../library/new_child`
* :doc:`../library/child`
* :doc:`../library/children`

