# WeatherPersistence25
Code for Graversen et al., Comm. Earth Env., 2025

The code can be found in GraversenEtAl25.tar.

Temperature persistence
Fig1, Fig5 and FigS1 
temperature persistence is based on surface-air temperature (SAT) fields of six-hourly resolution. 

Trend
Trends are based on difference between two 15 year periods 

SAT_spatialRunMean.sh
Uses: SpaceRunMean.py and tools_prep.py
-- 2D-smoothing of the SAT field over latitude and an equal distance in longitude.

SAT_Climatology.sh 
Input files from: SAT_spatialRunMean.sh
-- Calculate 5-year running-mean daily climatology.

WeathVar.py
Input files from: SAT_Climatology.sh 
-- Calculate running mean of climatology and anomalies. Save in latitude bands. 

WeathVar_PersAnom_MC.sh
Uses: WeathVar_PersAnom_MC.py and WeathVar_PersAnom_MCcollect.py
Input data from: WeathVar.py and WarmArctic.py
-- Calculate statistical significance of temperature persistence as shown in Fig5

PersAnom.Fig1.FigS1:
Input files from: WeathVar.py and WeathVar_PersAnom_MC.sh 
-- Calculate trends in weather persistence and plot Fig1 and FigS1. 

Arctic extreme events
Composite difference between 3-month warm and cold Arctic events. 

WarmArctic.py
Input files from: Climatology_MM.sh
-- Calculate 3-month warm and cold Arctic (north of 60 N) events 

WeathVar_PersAnomExt_MC.sh
Uses: WeathVar_PersAnomExt_MC.py and WeathVar_PersAnomExt_MCcollect.py
Input data from: WeathVar.py and WarmArctic.py
-- Calculate statistical significance of temperature persistence as shown in Fig5

Fig1PersAnomArcticExt.Fig5.py
Input files from: WeathVar.py, WarmArctic.py, and WeathVar_PersAnomExt_MC.sh
-- Calculate composite difference of 3-month warm and cold Arctic events of temperature persistence, and plot Fig. 5 

Surface-air temperature (SAT), zonal mass flux (uM), and geopotential height at 500 hPa (Z)
Fig2, Fig4, and FigS3

uMmm.sh
-- Calculate a mass-flus correction of uM and provide monthly data

Climatology_MM.sh
Input files from: uMmm.sh
-- Calculate 5-year running-mean and all-year monthly climatologies. 

Trends 
Trends are based on difference between two 15 year periods. 

Trend.Fig2.FigS3.py
Input files from: Climatology_MM.sh
--  Calculate trends in SAT, uM, and Z and plot Fig2 and FigS3.

Arctic extreme events 
Composite difference between 3-month warm and cold Arctic events. 

ArcticExt.Fig4
Input files from: Climaology_MM.sh
-- Calculate composite difference over 3-month Arctic warm and cold events and plot Fig4.

Spatial correlation of temperature persistence and M
Fig3

Fig3.py
Input data from: PersAnom.Fig1.FigS1.py, PersAnomArcticExt.Fig5.py,
                            Trend.Fig2.FigS3.py, and ArcricExt.Fig4.py
-- Calculate spatial correlation between trends and composite differences of temperature persistence and uM, and plot Fig3

Day-lag composites of temperature persistence, uM and dZ500
Fig6
Composites difference is over 3-month Arctic warm versus cold events.
dZ500 difference between Arctic and mid-latitude 500 hPa geopotential height.

uMdm.sh
-- Calculate a mass-flus correction of uM and provide daily data

Climatology_DM.sh
Input files from: uMdm.sh
-- Calculate 5-year running-mean daily climatologies for uM and Z. 

WeathVar.uM.Z.py
Input files from: Climatology_DM.sh 
-- Calculate running mean of climatology and anomalies of uM and Z. Save in latitude bands.

Weath_PersAnomExtRoll.sh
Uses: Weath_PersAnomExtRoll.py and  Weath_PersAnomExtRollcollect.py
Input files from: WeathVar.py and WarmArctic.py
-- Calculate temperature persistence over a 90 day period shifting relative to first day of Arctic
warm and cold 3-month events. The calculation is accomplished for days 130 days before and after day zero (first day of events).  

Weath_PersAnomExtRoll_MC2.sh
Uses: BS_MC.py, Weath_PersAnomExtRoll_MC2.py, and Weath_PersAnomExtRoll_MCcollect2.py
Input data from: WeathVar.py and WarmArctic.py
-- Calculate statistical significance of temperature persistence as shown in Fig6

Weath_uMExt_MC.sh
Uses: Weath_uMExt_MC.py and Weath_uMExt_Mccollect.py
Input data from: WeathVar.uM.Z.py and WarmArctic.py
-- Calculate statistical significance of uM as shown in Fig6.

ExtRolling_Fig6.py
Input files from: Weath_PersAnomExtRoll.sh, 
Input files significance: Weath_PersAnomExtRoll_MC2.sh and Weath_uMExt_MC.sh
-- Calculate uM and dZ500 relative to first day of Arctic warm and cold 3-month events. The calculation is accomplished for days 130 days before and after day zero (first day of events). Plot Fig6.


Day-lag regressions, of temperature persistence, uM and dZ500
Fig7
regressions and outo-regression of dZ500 on temperature persistence, uM and dZ500.

PersAnom_Regress.sh
Uses: PersAnom_Regress.py and PersAnom_RegressCollect.py
Input files from: WeathVar.py and WarmArctic.py
--  Calculate regression of dZ500 on temperature persistence as a function of a time lag in days.

PersAnom_Regress_MC2.py
Input data from: WeathVar.py WeathVar.uM.Z.py, and WarmArctic.py
-- Calculate statistical significance of temperature persistence and uM as shown in Fig7.

ExtRollingRegress_Fig7.py
Input files from: PersAnom_Regress.sh 
Input files significance: PersAnom_Regress_MC2.py
-- Calculate regression of dZ500 on uM and auto-regression of dZ500 as a function of a time lag in days. Plot Fig7.
