<ins>**WeebzSlayer_ArmyKnife**<ins>

Ez retroporter & toolshed


The process of retroporting can be very discouraging at first for beginners and for experienced players it remains the same boring task of filling and modifying paths, dbc editing and sql editing... 
This army knife was made to simplify the differents steps you need to retroport items, creatures, create a mounts, fix m2 particles and convert OBJ to M2.

<ins>**Item_Retroport**<ins>

I will go through all the tedious steps still required to import the dbcs and the sql. If you already have retroported items; this tool should make the process faster and less boring (I guess).

1- Fill every case with the values that correspond to the item dbcs tables and sqls tables.

2- Make sure the path ends with .mdx for the Modelname_1. item/objectcomponents/weapon/example.mdx

3- Texture_1 and Texture_2 doesn't require .blp at the end of the path. only write the model name.

4- Copy the item.dbc. Open notepad and paste it. Save the text file as item.csv
Copy the itemdisplayinfo.dbc. Open notepad and paste it. Save the text file as itemdisplayinfo.csv
Copy the server sql item_template. Open notepad and paste it. Save the text file as item_template.sql

5- Open your server data folder where item.dbc is located. Open item.dbc with Wdbx. In Wdbx click on "import". Click "from CSV" and locate the item.dbc file you saved in step 4. Click on ok. Click on save. Quit Wdbx. copy your new item.dbc updated and put it somewhere you will need it for your client patch.

Open your server data folder where itemdisplayinfo.dbc is located. Open itemdisplayinfo.dbc with Wdbx. In Wdbx click on "import". Click "from CSV" and locate the item.dbc file you saved in step 4. Click on ok. Click on save. Quit Wdbx. Copy your new itemdisplayinfo.dbc updated and put it somewhere you will need it for your client patch.

For item_template.sql I will use HeidiSQL and Azerothcore. Start HeidiSQL. Select your acore_world/item_template table. Start a new request query paste the item_template.sql you previously saved in step 4. Run the query.

6- Last step will be the patch step. Open MPQeditor. Create a new patch. Patch-w for example. Indicate the path of your item objectcomponents and other files required for his retroporting (they should be in the same file directory). Click on "ok". Add a bigger size for the patch. Click on "ok". Now click on create a new folder. Create a new folder. Name it "DBFilesClient". Click on the new DBFilesClient folder and click on add files. Add your item.dbc and itemdisplayinfo.dbc updated that you saved in step 5.
Quit MPQeditor.

7- Move your Patch-w in your Client Data folder. Start the game spawn the item with .additem (replace this by the ID in itemtemplate.sql)

== Congratulation. Your new item is now retroported! ==

== WIP == This app is finished I just need to finish the Readme.

Thanks to iThorgrim for the m2_particle_fix inspiration.
Thanks to August for being a friend in this community.
Thanks to manmadedrummer for the previous inspiration.
Thanks to Titi for the multiple helps in the past.
A special shout out to the weirdo reddit mod and any of these rejects.

One last thing I made this UI on purpose to mock the ego of some of these so called devs in the modding community. You're taking yourself too seriously chill. 
To laugh at oneself is to embrace humility.
