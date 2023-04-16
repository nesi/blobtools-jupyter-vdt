# Launch BlobTools2 viewer via JupyterHub Virtual Desktop

!!! jupyter "1. Install"
    1. Start a Jupyter server session via https://jupyter.nesi.org.nz/. 
        - Ideally with <KBD>4CPUs</KBD> and <KBD>8GB</KBD> of memory 
    
    2. Click  <KBD>Virtual Desktop</KBD> icon
       <center>![image](./nesi_images/vdt_icon.png)</center>
    
    3. Open a <KBD>Terminal</KBD> session on Virtual Desktop and procees with the installation 
        - Installation can be done via any terminal and not restricted to virtual desktop terminal 

        - change path to nobackup as we are going to create a python virtual environment which will consume a reasonable amount of Inodes.
            ``` 
            cd /nesi/nobackup/nesi12345/
            ```
        - Load a python module
            ```
            
            module purge
            module load Python/3.10.5-gimkl-2022a
            ```
        - Create a virtual environment
            ```
            python -m venv blobtools2
            ```
        - Activate the environment
            ```
            source blobtools2/bin/activate
            ```
        - Install `blobtoolkit[full]`
            ```
            pip install blobtoolkit[full]
            ```
        - Although installing `[ful]` should take care of the extensions, we recommend installing `[host]` as a standalone command 
            ```
            pip install blobtoolkit[host]
            ```
!!! jupyter "2. Create a sample dataset and test"

    These instructions are extracted from the [official BlobToolKit support documentation](https://blobtoolkit.genomehubs.org/blobtools2/blobtools2-tutorials/creating-a-dataset/) 