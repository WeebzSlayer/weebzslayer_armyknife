![TypeScript](https://img.shields.io/badge/TypeScript-95%25-blue)
![Java](https://img.shields.io/badge/Java-2.5%25-red)
![HTML](https://img.shields.io/badge/HTML-2.5%25-orange)

# ⚔️ WeebzSlayer_ArmyKnife 🛠️

> **Ez retroporter & toolshed**

## 👨‍💻 About The Project

The process of retroporting can be very discouraging at first for beginners. Even for experienced players, it remains the same boring task of filling and modifying paths, DBC editing, and SQL editing... It's not a complicated app but it is handy and some people would make you pay (bonkers!) for this lol.

**WeebzSlayer_ArmyKnife** was made to simplify the different steps you need to:
*   Retroport Items & Creatures 👹
*   Create Mounts 🐎
*   Fix M2 particles ✨
*   Convert `OBJ` to `M2` 🧊

---

## 🚀 Features

*   **Automated Workflow:** Skips the tedious manual entry.
*   **Plug & Play:** Ready to use immediately.
*   **Multi-Tool:** Handles DB, SQL, and Model tasks in one UI.

---

## 📖 Item_Retroport Documentation

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
    .additem [ID_FROM_SQL]
    ```

**Congratulations! Your new item is now retroported!** 🎉

---

## 🚧 Work In Progress (WIP)

This app is ready **Plug and Play**. I just need to finish the Readme.

---

## 👾 Credits & Acknowledgements

*   **iThorgrim**: For the `m2_particle_fix` inspiration.
*   **ayahne**: For the `m2_particle_fix` python script .
*   **Sylian**: For the `OBJ_to_M2` tutorial.
*   **August**: For being a friend in this community.
*   **manmadedrummer**: For the previous inspiration.
*   **Titi**: For the multiple helps in the past.
*   💀 Special shout out to the weirdo reddit mod and any of these preposterous individuals. I'm not going to acknowledge the popular crackhead that thought I was part of the hate mob against him lol.

---

## 📠 Author's Note

> "One last thing. I made this UI on purpose to mock the ego of some of these so-called devs in the modding community. You're taking yourself too seriously you need to chill lol. To laugh at oneself is to embrace humility."

### 🔓 License
**Free and Open Source.** 🏴‍☠️
