## Meta 

Base URL: `https://www.gran-turismo.com/us/gtsport/module/community/meta/`

### Description
Meta is a GET resource that provides objects and strings that are used throughout the website and in some cases referenced via api responses.

This can include things like manufacturer country tags, car categories, and even region codes for all the countries supported for FIA racing.

Example:
```
{
   "manufacturer":{
      "3":{
         "code":"90f2dd2aaa6c6882d317bfacfb137514",
         "tag":"10003",
         "country_tag":"63",
         "sort":2,
         "isMFCManufacturer":true
      }
   }
}
```

### Related Resources
* [localize](localize.md)
* [tags](tags.md)
