# kibord
## linuks keyboard layout mapping help (vindoz help in nekst section) 

```
/usr/share/X11/xkb $ ls
compat  geometry  keycodes  rules  symbols  types
/usr/share/X11/xkb $ ls -l symbols/zi
-rw-rw-r-- 1 viml viml 32327 Jul  7  2021 symbols/zi
/usr/share/X11/xkb $ cat symbols/zi
default  partial alphanumeric_keys modifier_keys
xkb_symbols "basic" {
    name[Group1]= "skovz";
    key <AD01> {  [    A,  q     ]  };
    key <AD02> {  [    D,  w     ]  };

    key <AD05> {  [    t,  X     ]  };  

    key <AC01> {  [    a,  Q     ]  };  
    key <AC03> {  [    d,  W     ]  };  

    key <AC06> {  [    h,  J     ]  };  
    key <AC07> {  [    H,  j     ]  }; 
    
    key <AB02> {	[	  T,	x		]	};

};


/usr/share/X11/xkb $ vi rules/base.lst  # search for ! layout
# in this section add entry :
! layout
us              English (US)
zi              skovz
```
some important xkb points:[custom keyboard xkb guide][xkblink1]
to add a keyboard layout to /usr/share/X11/xkb/rules/evdev.xml

1. go to end of <layoutList> section (search for </layoutList>).
2. Add the folloving after the last </layout> tag

```
<layout>
   <configItem>
      <name>zi</name>
      <shortDescription>india_phonetical_zinglish</shortDescription>
      <description>india_phonetical_zinglish</description>
      <languageList>
         <iso639Id>inc</iso639Id>
      </languageList>
      <countryList>
         <iso3166Id>IN</iso3166Id>
      </countryList>
   </configItem>
   <variantList/>
</layout>
```
3. invoking niyu evdev, either by **sudo dpkg-reconfigure xkb-data**
3.  or by deleting the xkm files in /var/lib/xkb and either logging out and back in or just switching to a new layout and back

[xkblink1]: https://people.uleth.ca/~daniel.odonnell/blog/custom-keyboard-in-linuxx11
