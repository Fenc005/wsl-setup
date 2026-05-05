# WSL SETUP 
## Foraussetzungen
* Virtualisierung soll im BIOS aktiviert sein
* VS soll installiert sein, und sollte nicht zu viele vorherige modifizierte Einstellungen haben, da es zu Fehler führen könnte

<details>
<summary> <h2> WSL installieren </h2> </summary>

1. Systemsteuerung öffnen

2. Programme

3. Windows-Features aktivieren oder deaktiveren

4. Features aktiveren

	* Windows-Hypervisor-Plattform

	* Windows-Subsystem für Linux

	* Plattform für virtuelle Computer

	* Danach Computer neu starten

5. CMD/Powershell als Administrator ausführen

	* `wsl --install` in CMD/Powershell ausführen

	* Standard Distro ist Ubuntu

6. Installationsassistent folgen

   * Username eingeben (WSL Nutzer)

   * Passwort eingeben (WSL Passwort)

7. CMD/Powershell schließen und dann ohne Admin rechte ausführen (sonst geht copy paste anscheinend nicht)

8. `wsl` in CMD eingeben, dann sollte sich WSL öffnen
</details>

<details>
<summary> <h2> Linux Setup </h2> </summary>

1. alles Updaten

	* `sudo apt update && sudo apt upgrade -y`

2. utilities installieren

	* `sudo apt install git -y`

	* `sudo apt install valgrind -y`

	* `sudo apt install clang -y`

</details>

<details>
<summary> <h2> Gitlab Setup innerhalb von WSL </h2> </summary>

1. Username und E-Mail einrichten

	* `git config --global user.name "Vorname Nachname"`

	* `git config --global user.email "Studenten E-Mail"`

2. SSH Key erstellen

	* `ssh-keygen -o -t rsa -b 4096`

		- dort alles einfach leer lassen

3. Ins SSH ordner gehen

	* `cd .ssh/`

4. Öffnen und Kopieren

	* `cat id_rsa.pub`

		- Markieren und dann kopieren mit **[strg + shift + c]**

5. Bei Gitlab anmelden und das SSH Key einrichten

	* Profilbild anklicken

	* **Edit Profile** auswählen

		- Access --> SSH Keys --> Add new Key --> Neues Key bei Key Feld einfügen --> **Add new Key** anklicken
</details>

<details>
<summary> <h2> VS Code Setup </h2> </summary>

1. Extensions

	* [WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)

	* [C/C++ Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-extension-pack)

	* [CodeLLDB](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb)

2. User Settings Json

	* Bei der Suchleiste oben in der Mitte `> Preferences: Open User Settings (JSON)` eingeben

	* Das dann dort einfügen

		```Json
		{
		"workbench.colorTheme": "Dark 2026",
		"workbench.editor.useModal": "off",
		"workbench.list.openMode": "singleClick",
		"workbench.startupEditor": "none",
		"editor.tabSize": 2,
		"editor.rulers": [
			60,
			120,
			180,
			240, 
			300
		],

		"workbench.secondarySideBar.defaultVisibility": "hidden",
		"editor.stickyScroll.enabled": false,
		"terminal.integrated.stickyScroll.enabled": false,
		"terminal.integrated.initialHint": false,
		"editor.fontLigatures": false,
		"terminal.integrated.fontFamily": "monospace",
		"editor.fontFamily": "'Cascadia Code', 'Courier New', monospace",
		"workbench.tree.enableStickyScroll": true,
		"workbench.tree.renderIndentGuides": "none",
		"workbench.tree.indent": 16,
		"explorer.compactFolders": false,
		"editor.minimap.autohide": "scroll",
		"C_Cpp.default.cppStandard": "c++20",
		"C_Cpp.default.cStandard": "c17",
		}
		```
3. CMD öffnen und WSL starten ```wsl```

4. Dann innerhalb von WSL ```code . ``` eingeben
</details>
