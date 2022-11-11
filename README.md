# Weather Alerts Library

## A library written in TypeScript for recieving weather alerts from several different countries.

### Currently supported countries:

- [x] United Kingdom (Met Office)
- [x] United States (National Weather Service)*1
- [ ] Canada (Enviroment Canada / Alert Ready)
- [x] New Zealand (MetService)
- [ ] Australia (Bureau of Meteorology) *2
- [x] Ireland (Met Éireann)
- [ ] Germany (Deutscher Wetterdienst)*3
- [ ] France (Météo France)*3
- [ ] Netherlands (KNMI)*3
- [ ] Belgium (Royal Meteorological Institute of Belgium)*3
- [ ] Denmark (Meteorological Institute of Denmark)*3
- [ ] Norway (Meteorological Institute of Norway)*3
- [ ] Sweden (SMHI)*3
- [ ] Finland (Finnish Meteorological Institute)*3
- [ ] Spain (AEMET)*3
- [ ] Portugal (IPMA)*3
- [ ] Italy (Agenzia Nazionale per le Forecast e la Meteorologia)*3
- [ ] Switzerland (MeteoSwiss)*3
- [ ] Austria (ZAMG)*3
- [ ] Poland (Polish Meteorological Service)*3

*1 - The parser I use for XML > JSON excludes all entries prefixed with "cap:", meaning data such as effective, expires, onset, urgency, etc. are not included. I am working on a fix for this, however I am not sure if it will be possible. All help is appreciated.  
*2 - The Bureau of Meteorology code is written, however, it results in a 403 error. I am unsure if this is my fault or TBOM's fault.  
*3 - MeteoAlarm is used for these countries. And it threw a 406 error. How is it not acceptable? I have no idea. I am working on a fix for this.

### How to use:

```typescript
import { MetOffice } from "weather-alerts";

MetOffice.getAlerts().then(alerts => {
    console.log(alerts);
});
```

### Notices:

- Most of the time, the meterological offices in the supported countries will require you to link to any active alerts. Please check the terms and conditions of the weather alert service you are using before using this library.
- This library is not affiliated with any of the weather alert services listed above.
- Some of the alerts may not be in English. This is due to the fact that the weather alert services do not provide an English translation of the alert. This library will return the alert in the language it is provided in. However, the following countries do provide an English translation of the alert: United Kingdom, United States, New Zealand, Australia, Ireland.
