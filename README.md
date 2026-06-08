# ViaStitching for KiCad 10

A pure-python Via Stitching action plugin for KiCad's PCB editor (pcbnew).

This is a trimmed fork of [js-reynaud/kicad-action-scripts](https://github.com/jsreynaud/kicad-action-scripts):
everything except the Via Stitching plugin has been removed, and the version
detection has been fixed so it runs on **KiCad 10**.

> KiCad 10 still ships the legacy SWIG `pcbnew.ActionPlugin` API this plugin uses.
> That API is deprecated and is scheduled for removal in KiCad 11, at which point
> a rewrite to the IPC API (`kicad-python`) will be required.

## Install

Copy (or symlink) this whole directory into your KiCad plugins folder, then restart
pcbnew or use *Tools → External Plugins → Refresh Plugins*.

The exact path is shown in pcbnew under *Tools → External Plugins → Open Plugin Directory*.
Typical locations:
 - Windows: `%USERPROFILE%\Documents\KiCad\10.0\3rdparty\plugins\`
 - Linux: `~/.local/share/kicad/10.0/scripting/plugins/` (or `~/.kicad_plugins/`)
 - macOS: `~/Documents/KiCad/10.0/scripting/plugins/`

## Usage

Select **Via Stitching Generator** in the Tools menu (or its toolbar button),
choose your options in the dialog and run.

![The interface](images/via1.png)

Result:

![The result](images/via2.png)

## Known issues

 - Vias cannot be deleted automatically. The plugin creates a group named
   `ViaStitching <net>` that owns all generated vias — select one via to select
   the group, then press Delete.

## License

GPL v2 or later — see [LICENSE.md](LICENSE.md).
