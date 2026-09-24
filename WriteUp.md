# Forensic-Analysis-Windows-11-VM
This is a written report of how I built a forensic analysis virtual machine to create a safe curated space for personal digital forensic lab work. 

### Setup
- **Host**: Windows 11 pro running Hyper-V on 32GB of Ram
- **VM**: 12 GB static Ram, 250 GB disk, TPM on
- **Checkpoints**: Standard checkpoints on, automatic checkpoints disabled
- **Guest Services**: Disabled

  <img width="1919" height="1198" alt="image" src="https://github.com/user-attachments/assets/b23acc99-dca7-49b0-8adc-23f6c80c18db" />


### Sept 21: VM Creation and 1st Tools
- Getting windows 11 iso was easily available on Microsoft's website. Booting the VM was relatively easy and the only hurdle I ran into was that TPM was not enabled at the start.
- After successful boot I downloaded the install script needed to download Eric Zimmerman tools. The script was successful but in order to run the tools I need to download the .NET9 Runtime. 
- Following this I completed my download of Hayabusa
- I attempted to download Chainsaw but after an attempt to run it the program failed silently 
  
  ### Sept 23: Fix Chainsaw and Continue Tool Downloads 
- Chainsaw continued to fail silently so I ran $LASTEXITCODE. This returned -1073741515 signifying a need to download VC++
- After this I installed the following:
	- Wireshark
	- FTK Imager
	- KAPE
	- git
	- DeepBlueCLI
	  

### Sept 24: Finish Installing Tools/Building VM
- These are the tools that I installed to finish off my workspace
	- RegRipper4.0: Accidently downloaded the wrong version but resolving was simple
	- Velociraptor
	- Python 3.12
	- Volatility3
	- Autopsy
	- NetworkMiner
- Prior to downloading any evidence I created a cases folder at C:\Cases and excluded it from the Microsoft Defender

  <img width="916" height="887" alt="image" src="https://github.com/user-attachments/assets/760c91ae-b4d0-408e-b303-ff1b95046594" />

	- Due to the fact that some images may contain real malware we do not want Defender to quarantine evidence
- I then created a VM checkpoint for a baseline
- Heres what the tool list so far looks like

<img width="1007" height="885" alt="image" src="https://github.com/user-attachments/assets/47239480-425a-4d89-a86f-0e8bb44bfcd6" />


  ### What I would tell someone trying to do this after my experience
  - Install .NET9 and the Microsoft VC++ Redistributable before downloading forensic tools
  - Zips downloaded from the internet might get flagged by windows so run Unblock-File prior to extraction
  - Take checkpoints before big changes

  

  
