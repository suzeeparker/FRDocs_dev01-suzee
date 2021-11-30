
1. Set System Path to contain: C:\repos\FormR\_2\bin
   - Click Start, type env, select: Edit the system environment variables
   - Click on button, Environment Variables
   - Under System (not User) variables, select Path, then click Edit...
   - Click on button, New, then type: C:\repos\FormR\_2\bin
   - Click Ok three times

2. Get FormR Tools from 8020data GitHub repository
   - From Windows command prompt enter: bash
   - $ cd C:/Repos/FormR
   - $ git https://github.com/8020data/FRTools.git     tools

3. Create a link from ./FormR/_2  ./FormR/tools/_2 to
   - Open Windows Command prompt Run as Administrator  screen shot 
   - > cd C:\Repos\FormR
   - > mklink /d _2 tools\_2

4. Run FRTools command
   - $ frt  



