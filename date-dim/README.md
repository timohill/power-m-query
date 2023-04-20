# Date Dim

Devleoped in Power M Query

The Date dimension (DateDim) is a lookup for using dates as a filter in Power BI.

The following additions can filter based on Hardcoding, MinMax on the fact tables, or Parameterisation.

/** Scope ************************************************************************/ 
    // hardcoded date range
    
    vStartDate = #date(2018,6,1), 			// you can set this to 1st of cal or fin yr
    vEndDate = #date(2019,12,31), 
	
	
/** Scope ************************************************************************/ 
    // using min/max of facts for date range
       
    MinYear = Date.Year(List.Min(Table.Column(<<tablename>>,"<<fieldname>>"))),
    MaxYear = Date.Year(List.Max(Table.Column(<<tablename>>,"<<fieldname>>"))),

    vStartDate = #date(MinYear,1,1), 			// you can set this to 1st of cal or fin yr
    vEndDate = #date(MaxYear,12,31), 			
	
/** Scope ************************************************************************/ 
     // parameterised date range - create 2 parameters for Start Year and End Year
  
    vStartDate = #date(#"Start Year",6,1), 		// you can set this to 1st of cal or fin yr
    vEndDate = #date(#"End Year",12,31), 
	
