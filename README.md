# Diabetic-Macular-Oedema-development-and-therapy
Repository containing FEBio files to simulate oedema development and therapy response

Details of files
.dll file (Windows), .sh file (Linux) -  These are the plugin files written to extend the default model present in FEBio. Adding this plugin will give options to apply fluid and solute boundary conditions as described in the article. Please follow the FEBio documentation to import the plugin. 

.feb files - These are the FEBio model files developed for different cases presented in the article. 

Details of .feb file naming convention - 
1. Anti_VEGF_***.feb - Anti_VEGF indicates that the febio file has antiVEGF solute. Files starting with Anti_VEGF reproduces the results presented in sections 3.3 and 3.4 in the article. 
2. ***_Isotropic_***.feb - Isotropic indicates that the distribution of fibres is isotropic. It could otherwise be Vertical or Vert_Horizontal representing Vertical or Z-shaped fibres respectively. Different cases can simulate behaviour observed in sections 3.3 and 3.4 in the article.
3. Physiological_***.feb - Files starting with Physiological indicates the physiological state of the retina, without any BV leakage. These files simualte the behaviour presented in section 3.1.
4. BV_Leakage_***.feb - Files starting with BV_Leakage describes the condition of leakay blood vessels as simulated in section 3.2.
5. Restart_File_***.feb - Files starting with the Restart are used to simulate Anti_VEGF recovery. This is used to reduce the computational re-runs. A base case of blood vessel leakage is initially run upto a certain time. The output is stored. Then the program is restarted adding Anti_VEGF.

Method to reproduce the results:
1. Install FEBio. We have used FEBio V4.10 in this article.
2. Install the plugin (using the .dll file, if on windows and .sh file, if on Linux)
3. Run the desired febio file using the following command within the febio terminal : run -i ***.feb -p ***.xplt
4. .xplt is the format of the output file.  This can later be viewed through FEBio GUI.
