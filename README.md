![TypeScript](https://img.shields.io/badge/TypeScript-95%25-blue)
![Java](https://img.shields.io/badge/Java-2.5%25-red)
![HTML](https://img.shields.io/badge/HTML-2.5%25-orange)

# ⚔️ WeebzSlayer_ArmyKnife 🛠️


> **Ez retroporter & toolshed**


![banner](https://github.com/user-attachments/assets/3cb39e7e-f727-4cdd-9e47-2f3de10cf97e)


## 👨‍💻 About The Project

The process of retroporting can be very discouraging at first for beginners. Even for experienced modders, it remains the same boring task of filling and modifying paths, DBC editing, and SQL editing... This app is not complicated once you understood the key steps in retroporting. This app would be handy and some people would make you pay for this "I have a private tool" smh... I also made the DBC editing and SQL editing only possible for one item or one creature at a time on purpose. It can be hell to go back to some **TextureVariations** missmatching when you have the wrong path or name entered after entering 20 rows or sum...

**WeebzSlayer_ArmyKnife** was made to simplify the different steps you need to:
*   Retroport Items⚔️ & Creatures👹
*   Create Mounts 🐎
*   Fix M2 particles ✨
*   Convert `OBJ` to `M2` 🧊

---

## 🚀 Features

*   **Automated Workflow:** Skips the tedious manual entry. Copy,save and import.
*   **Plug & Play:** Ready to use immediately. Download weebzslayer_armyknife1.1.0 in releases and start it.
*   **Multi-Tool:** Handles DB, SQL, and Model tasks in one UI.

---

## 📋 Requirements

*   **AzerothCore**: [GitHub Repository](https://github.com/azerothcore)
*   **WDBX Editor**
*   **HeidiSQL** (or similar database manager): [Download](https://www.heidisql.com/download.php)
*   **MPQEditor**
*   **Notepad++** *(Optional)*: [Download](https://notepad-plus-plus.org/downloads/)
*   *Disable auto-update. If you know you know.* 🧸😉

---

## ⚔️ Item_Retroport Documentation

I will go through all the tedious steps still required to import the DBCs and the SQL. If you already have retroported items, this tool should make the process faster and less boring (I guess).

### 🛠️ Step-by-Step Guide

1.  **Fill Data:** Fill every case with the values that correspond to the **item dbcs tables** and **sqls tables**.
2.  **Model Paths:** Make sure the path ends with `.mdx` for the `Modelname_1`.
    *   *Example:* `item/objectcomponents/weapon/example.mdx`
3.  **Textures:** **Texture_1** and **Texture_2** do not require `.blp` at the end of the path. Only write the model name.
4.  **Exporting Files:**
    *   Copy the `item.dbc`. Open Notepad, paste it, and save as `item.csv`.
    *   Copy the `itemdisplayinfo.dbc`. Open Notepad, paste it, and save as `itemdisplayinfo.csv`.
    *   Copy the server SQL `item_template`. Open Notepad, paste it, and save as `item_template.sql`.

### 💾 Database & SQL Injection

5.  **WDBX Import:**
    *   **Item.dbc:** Open your server data folder. Open `item.dbc` with **Wdbx**. Click **Import** > **From CSV** and select the `item.csv` from Step 4. Click **OK**, then **Save**.
    *   **ItemDisplayInfo.dbc:** Repeat the process. Open `itemdisplayinfo.dbc` with **Wdbx**. Click **Import** > **From CSV**, select `itemdisplayinfo.csv`. Click **OK**, then **Save**.
    *   *Note:* Copy your updated `.dbc` files and put them somewhere safe for your client patch.

    *   **SQL:** Open **HeidiSQL** (or your preferred manager). Select your `acore_world/item_template` table. Start a new query tab, paste the `item_template.sql` from Step 4, and **Run** the query.

### 📦 Patching (MPQEditor)

6.  **Create the Patch:**
    *   Open **MPQEditor**. Create a new patch (e.g., `Patch-w.mpq`).
    *   Indicate the path of your `item/objectcomponents` and other files required for the retroport (ensure they are in the same directory). Click **OK**.
    *   Add a bigger size for the patch. Click **OK**.
    *   **DBFilesClient:** Click "Create a new folder" inside the MPQ. Name it `DBFilesClient`.
    *   Add your updated `item.dbc` and `itemdisplayinfo.dbc` (saved in Step 5) into this folder.
    *   Quit MPQEditor.

### 🎮 Final Step

7.  **Deployment:**
    *   Move your `Patch-w` into your Client `Data` folder.
    *   Start the game and spawn the item:
    ```bash
    .additem [ID_item_template_SQL]
    ```

**Congratulations! Your new item is now retroported!** 🎉

---

## 👹 Creature_Retroport Documentation

I will go through all the tedious steps still required to import the DBCs and the SQL. If you already have retroported creatures, this tool should make the process faster and less boring (I guess).

### 🛠️ Step-by-Step Guide

1.  **Fill Data:** Fill every case with the values that correspond to the **creature dbcs tables** and **sqls tables**.
2.  **Model Paths:** Make sure the path ends with `.mdx` for the `Modelname`.
    *   *Example:* `creature/example/example.mdx`
3.  **Textures:** **Texturevariation_1**, **Texturevariation_2** and **Texturevariation_3** do not require `.blp` at the end of the path. Only write the model name.
4.  **Exporting Files:**
    *   Copy the `creaturemodelinfo.dbc`. Open Notepad, paste it, and save as `creaturemodelinfo.csv`.
    *   Copy the `creaturedisplayinfo.dbc`. Open Notepad, paste it, and save as `creaturedisplayinfo.csv`.
    *   Copy the server SQL `creature_model_info`. Open Notepad, paste it, and save as `creature_model_info.sql`.
    *   Copy the server SQL `creature_template`. Open Notepad, paste it, and save as `creature_template.sql`.

### 💾 Database & SQL Injection

5.  **WDBX Import:**
    *   **Creaturemodelinfo.dbc:** Open your server data folder. Open `creaturemodelinfo.dbc` with **Wdbx**. Click **Import** > **From CSV** and select the `creaturemodelinfo.csv` from Step 4. Click **OK**, then **Save**.
    *   **Creaturedisplayinfo.dbc:** Repeat the process. Open `creaturedisplayinfo.dbc` with **Wdbx**. Click **Import** > **From CSV**, select `creaturedisplayinfo.csv`. Click **OK**, then **Save**.
    *   *Note:* Copy your updated `.dbc` files and put them somewhere safe for your client patch.

    *   **SQL (Model Info):** Open **HeidiSQL** (or your preferred manager). Select your `acore_world/creature_model_info` table. Start a new query tab, paste the `creature_model_info.sql` from Step 4, and **Run** the query.
    *   **SQL (Template):** Open **HeidiSQL**. Select your `acore_world/creature_template` table. Start a new query tab, paste the `creature_template.sql` from Step 4, and **Run** the query.

### 📦 Patching (MPQEditor)

6.  **Create the Patch:**
    *   Open **MPQEditor**. Create a new patch (e.g., `Patch-v.mpq`).
    *   Indicate the path of your `creature/example` and other files required for the retroport (ensure they are in the same directory). Click **OK**.
    *   Add a bigger size for the patch. Click **OK**.
    *   **DBFilesClient:** Click "Create a new folder" inside the MPQ. Name it `DBFilesClient`.
    *   Add your updated `creaturemodelinfo.dbc` and `creaturedisplayinfo.dbc` (saved in Step 5) into this folder.
    *   Quit MPQEditor.

### 🎮 Final Step

7.  **Deployment:**
    *   Move your `Patch-v` into your Client `Data` folder.
    *   Start the game and spawn the creature:
    ```bash
    .npc add [ID_creature_template_SQL]
    ```

**Congratulations! Your new creature is now retroported!** 🎉

---

## 🐎 Mount_Creator Documentation

Work in Progress. Documenting process engaged `beep beep`... BOOOOooooooring huh!

---

## ✨ M2_Particle_Fix Documentation

### 🛠️ Step-by-Step Guide

1.  **Input:** Drag & Drop your broken `.m2` file.
2.  **Et voilà!** Nothing more to do, the file is fixed!
    *   A **green success message** should appear on the right screen log.
    *   If it failed, you will see a **red message** detailing the error on the right screen log.

---

## 🧊 OBJ_to_M2 ✨ Documentation

### 🛠️ Step-by-Step Guide

1.  **Source:** Drag & Drop your OBJ in **SOURCE_OBJ**.
2.  **Texture:** Drag & Drop your TEXTURE in **TEXTURE_REF**.
3.  **Fill Data:** Fill the `ingametexturepath`.
    *   *Example:* `item/objectcomponents/weapons/`
    *   *Warning:* Path will be injected into M2 header offset `0x58`.
4.  **Convert:** Click on **INITIALIZE_CONVERSION**. The processes should start.
    *   The **status_monitor** should turn green and the screen log should start.

**Your OBJ has been successfully converted to M2! Hurray!** 🎉

---

## 🚧 Work In Progress (WIP)

This app is ready **Plug and Play**🔌✅. I just need to finish the Readme.
Gonna add a sql sync with HeidiSQL. A very minor change is in the creature_retroport. I will have to change creaturemodel.dbc to creaturemodeldata.dbc. At the moment this isn't affecting anything tho. I will incorporate the M2Workshop from Wall in the WeebzSlayer_ArmyKnife1.1.1 next release. Thanks Wall!

---

## 👾 Credits & Acknowledgements

*   **iThorgrim**: For the `m2_particle_fix` inspiration.
*   **ayahne**: For the `m2_particle_fix` python script .
*   **Sylian**: For the `OBJ_to_M2` tutorial.
*   **August**: For being a friend in this community and having good ideas.
*   **Wall**: For the `M2Workshop` script.
*   **manmadedrummer**: For the previous inspirations.
*   **Titi**: For the multiple helps and patience.
*   💀 Special shout out to the weirdo reddit mod and any of these preposterous individuals. I'm not going to acknowledge the popular crackhead that thought I was part of the hate mob against him lol.

---

## 📠 Author's Note

> "One last thing. I made this UI on purpose to mock the ego of some "devs" in the modding community. You're taking yourself too seriously you need to chill lol. You're not helping us reverse entropy lol! To laugh at oneself is to embrace humility. The next project is the Logg/load_ing_Screens_Studio and I already have an idea for the UI.😂"

### 🔓 License
**Free and Open Source.** 🏴‍☠️

---
<p align="center"><img width="388" height="247" alt="wbzbanner" src="https://github.com/user-attachments/assets/d210117b-0361-41af-8095-756a645e95b0" />
</p>

