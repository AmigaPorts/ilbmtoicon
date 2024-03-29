# ilbmtoicon

  converts one or two ilbm image files into an amiga icon file
  which will contain both old style (pre 3.5) image data and
  new style image data (IFF ICON attached at the end).
  
  can also convert one or two png image files into a PNG icon
  file (normal PNG image with an extra icOn chunk). If two
  PNG images are specified, the resulting .info file will simply
  result in both images being joined together.
  
## usage

  ilbmtoicon DESCRIPTIONFILE IMAGE1 [IMAGE2] outfile
  
  If two images are specified, both must be of the same file
  format, ie. PNG or ILBM. The image format determines whether
  an Amiga style icon (ILBM) or a PNG style icon (PNG) will be
  created.
  
## icondescription file

  Is a text file which should be named ICONNAME.info.src.
  If the specified file does not exist this is silently ignored.
  
  It can contain the following options in the form of
  KEYWORD = KEYVALUE. 
  
   TYPE = (DISK|DRAWER|TOOL|PROJECT|GARBAGE|DEVICE|KICK|APPICON)
   
     Icon type. Optional. Default is TOOL. Not necessary/useless
     when making a PNG icon, because there the icon type is not
     stored, but guessed automatically when loaded by icon.library.
     
   DEFAULTTOOL = <string>
   
     Optional.
    
   STACK = <integer>
   
     Stack. Optional. Default is 4096.

   TOOLTYPE = <string>
   
     Can be used multiple times. Optional.
         
   ICONLEFTPOS = <integer>
   
     X Position of icon. Optional. Default is 0x80000000 (NO_ICON_POSITION).
     
   ICONTOPPOS = <integer>
   
     Y Position of icon. Optional. Default is 0x80000000 (NO_ICON_POSITION).
     

   DRAWERDATA = <anystring>
   
     Attach DrawerData struct to Icon. Optional.
   
   DRAWERLEFTPOS = <integer>
   
     X Position of Drawer Window. Optional.
      
   DRAWERTOPPOS = <integer>
   
     Y Position of Drawer Window. Optional.
     
   DRAWERWIDTH = <integer>
   
     Width of Drawer Window. Optional.
     
   DRAWERHEIGHT = <integer>
   
     Height of Drawer Window. Optional.
     
   DRAWERVIEWLEFT = <integer>
   
     X View Position of icons inside drawer window. Optional.
     
   DRAWERVIEWTOP = <integer>
   
     Y View Position of icons inside drawer window. Optional.
     
   DRAWERSHOW = (DEFAULT|ICONS|ALL)
   
     Show icons only for files having icons or for all files.
     Optional. Default = DEFAULT = only icons.
    
   DRAWERSHOWAS = (DEFAULT|ICON|TEXT_NAME|TEXT_DATE|TEXT_SIZE|TEXT_TYPE)
   
     View Mode. Icons or Text sorted by name/date/size/type.
     Optional. Default = DEFAULT = inherit from parent view
     mode.
     
   TRANSPARENT = <integer>
   
     Transparent (mask) color in ILBM image(s). Use -1 for no transparency.
     Default = 0.

