# This is an `<h1>` header, which is the largest

## This is an `<h2>` header

###### This is an `<h6>` header, which is the smallest

![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)

``` python
def get_ldbs_uinfo():
    ldbs_lst=[]
    lsep='# record'
    ldct={}

    dt_cp=subprocess.run(['ldbsearch','-H','ldap://127.0.0.1','-P','objectClass=user'],stdout=subprocess.PIPE)
    dt=dt_cp.stdout.decode('utf-8')
    ldbs=dt.splitlines()

    for ld in ldbs:
        if ld.startswith(lsep):
            if len(ldct)>0:
                ldbs_lst.append(ldct)
                ldct={}
        tstr=ld.split(':',maxsplit=1)
        if len(tstr)==2:
            val=tstr[1].strip()
        else:
            val=''
        ldct[tstr[0].strip()]=val
    return ldbs_lst
```

- [ ] Turn on GitHub Pages
- [ ] Outline my portfolio
- [ ] Introduce myself to the world
