# kibord
linuks vindoz keyboard layout mapping help

```
/usr/share/X11/xkb $ ls
compat  geometry  keycodes  rules  symbols  types
/usr/share/X11/xkb $ ls -l symbols/zi
-rw-rw-r-- 1 viml viml 32327 Jul  7  2021 symbols/zi
/usr/share/X11/xkb $ head -n 80 symbols/zi
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
