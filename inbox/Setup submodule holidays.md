 To set up your Source of Truth repository and link it as a submodule in your "Second Brain," please run these commands in your terminal.


  I have included a step to "clear the cache" of the existing vakantie folder, which is necessary because Git needs to know that the folder is
  now a separate project.

  Step 1: Create the new "Holidays" Repo


   1 # Move to your project root
   2 cd /Volumes/Samsung2TB/personal
   3
   4 # Create the new private repository on GitHub
   5 gh repo create holidays --private --description "Central Source of Truth for Holiday Planning"

  Step 2: Convert the folder to a Submodule


    1 # 1. Back up your existing holiday files to a temporary folder
    2 mv vakantie /tmp/vakantie_backup
    3
    4 # 2. Tell Git to "forget" the old vakantie folder (Crucial step!)
    5 git rm -r --cached vakantie
    6 git commit -m "chore: remove vakantie folder to prepare for submodule"
    7
    8 # 3. Add the new holidays repo as a submodule
    9 git submodule add https://github.com/wvdberge/holidays.git vakantie
   10
   11 # 4. Copy your holiday files back into the new submodule folder
   12 cp -r /tmp/vakantie_backup/* vakantie/

  Step 3: Push the files to the "Holidays" Repo


    1 # 1. Move into the new submodule folder
    2 cd vakantie
    3
    4 # 2. Ensure you are on the 'main' branch
    5 git checkout -b main
    6
    7 # 3. Add, commit, and push your holiday plans
    8 git add .
    9 git commit -m "feat(uk_cycling): initial upload of Hadrian's Cycleway 2026 plans"
   10 git push origin main

  Step 4: Link the change in your "Personal" Repo


   1 # 1. Go back to the root of your personal repo
   2 cd /Volumes/Samsung2TB/personal
   3
   4 # 2. Record the submodule addition
   5 git add .
   6 git commit -m "chore: convert vakantie folder to submodule linked to holidays repo"
   7
   8 # 3. Push everything to your main personal repository
   9 git push origin main

  ---


  What to check afterward:
   1. On GitHub: Go to https://github.com/wvdberge/holidays. You should see only your uk_cycling and other holiday folders.
   2. In your Editor: Open /Volumes/Samsung2TB/personal/DASHBOARD.md. You will notice that everything still works perfectly—you can still click
      links to your holiday files as if they were never moved!


  Let me know once you've run these, and I'll confirm the new structure is working correctly on my end.