---
description: The following metrics are synchronized as part of the appFigures integration.
title: Metrics and Dimensions
uuid: 419a9031-1291-4ec0-a2e1-93993858991a
exl-id: c32f1cd9-93fe-4091-994f-5e796162e02b
---
# Metrics and Dimensions{#metrics-and-dimensions}

The following metrics are synchronized as part of the appFigures integration.

|  Metric  | Description  |
|---|---|
|  App Store Downloads  | The number of mobile application downloads.  |
|  App Store Purchases (in app)  | The number of in-app purchases.  |
|  App Store Rank  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  App Store Rank Divisor  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  App Store Rating  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  App Store Rating Divisor  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  App Store Revenue (in app)  | The amount of in app revenue.  |
|  App Store Revenue (one off)  | The amount of revenue associated with the purchase of an app.  |
|  App Store Royalties (in app)  | Deprecated.  |
|  App Store Royalties (one off)  | Deprecated.  |

The following reserved classification dimensions are created by the data connectors wizard for the AppFigures Object ID reserved eVar.

|  Classification Dimension  | Description  |
|---|---|
|  Country Name  | The name of the country related to the app store activity.  |
|  Device Name  | The name of the mobile device related to the app store activity.  |
|  Appstore Name  | The name of the appstore that reported the activity.  |
|  Application Name  | The name of the mobile application.  |
|  In-app Name  | The item purchased within the application.  |
|  Category Name  | Primary category of the app in the app store.  |
|  Review Title  | Title of the review.  |
|  Review Comment  | Comment of the review  |
|  Application Version  | Version of the application that was used to generate the review.  |
|  App Store User  | Author (user name) of the review.  |

The following calculated metric is created by the data connectors wizard: 

| Calculated Metric | Description |
|--- |--- |
|App Store Average Rank (Numeric)|The average app ranking. This calculated metric is defined using the following formula:   `[App Store Rank]` / `[App Store Rank Divisor]` <br> Note:  The number of applications ranked per category and country varies between app stores. If your application is ranked lower than this threshold, application ranks are not available.|
|App Store Average Rating|The average app rating. This calculated metric is defined using the following formula:  `[App Store Rating]` / `[App Store Rating Divisor]`|

## Relevant Dimensions for Each AppFigures Metric {#section-cd356d3dce04412893beed345305c247}

The following table shows which report dimensions relate to which metrics.

<table id="table_B9CF57EABE22449FBF1963E3F105E702"> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> App Store Downlds </td> 
   <td> App Store Purchases (in-app) </td> 
   <td> App Store Rank </td> 
   <td> App Store Rank Divisor </td> 
   <td> App Store Rating </td> 
   <td> App Store Rating Divisor </td> 
   <td> App Store Revenue (in-app) </td> 
   <td> App Store Revenue (one-off) </td> 
   <td> App Store Avg. Rank </td> 
   <td> App Store Avg. Rating </td> 
  </tr> 
  <tr> 
   <td> Country Name </td> 
   <td> <p> <img id="image_8EBB60CD948E4C3D8424D563CABF8A8F" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_EBCE0E037E0B4B399D287BA1BEBCF9C8" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_4D52180A493C43D2866261C040FD617B" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_44A3C7383AF847E3B04B419E7470A475" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_69AEB1DA1A6C412B8A034E74591A022C" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_6418CFE0C305440288E3F0A26B63A311" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_794AD42792D740D1B6E17B31ACF8D627" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A869F470F5FB454B9EABA1C8FF7508B5" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_0625B254252B4DCE944499D27588320B" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_6E71CB8EEFBC41C2AE180FB6A3E8874C" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Device Name </td> 
   <td> <p> <img id="image_9693598D852F4DE1A3D59AF06C5F3DBA" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_ADD21EF2E6304797B0C7AFCB8008AAE6" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_D62BCDF5691645498A2F277C5DC44060" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_75610F3EF1F3439FB519AB96DD531B58" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_E77543DD9FDA4E718187A5E2005B3EE4" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_B705A151F87A4657B3D7315A8A471D3E" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_03F6AA1281C94BDFB77D14D5C87267A1" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_AF56149715B7472F8D458123EF213529" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_1DF9CCCD41824D508240F049D1EB64F0" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_6E5B220C71CD47CEBB9CE65FB42CC692" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Appstore Name </td> 
   <td> <p> <img id="image_B0382AE2E0A44D8BBB373E95061C96B7" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_653EE4DADF644E329EB948051AF511CC" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_16E4236EAAC64FC4872603974E61417B" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_047DA686AD9C4E11A7146E029A12DCF8" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_D866071B94A845D59400FCCC014D5E42" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_887E8B9DFB7E4689967F91F2F7B172C5" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_54185F7AB4B34352BEA4E81B658A0593" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_7F818D1F947049CBB91D2D672591C616" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_0ACD2CF6E6DA4F4AA5FC3FF0C64D1092" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_2D179B9724B945DB964EA42288431EEB" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> App Name </td> 
   <td> <p> <img id="image_241BAE06E2FD422C9DF81457B425BFB6" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_ACFE6C13353B4688903066F7828715B0" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_5E99AF2FC30E4AFFA5FFBC1EABDA0682" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_6B205D0239D74325B1F47640743529BC" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_92B066D854B74AFA908289A95316C15C" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_FB835DD42AD146D69EF600FEA049C235" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_8309721F0B0940BFBA298074EB196741" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_45850D6E433E46329CE75240D7DBA9C7" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_D449ABDA00F347DBABDB1FF9E038D757" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A3ABC80FB852406D9593F89DE7C3DBFD" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> In-app Name </td> 
   <td> <p> <img id="image_4BC8937C23A24BDCB760841BF8C02E29" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_68B43745C8284A44BA589825CAC9DABE" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A107ECAE1D154976A2FF9A8AB5746377" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A070A5C7C8BA4D349215166D340EC7D6" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A3A0484F09A04FD496DFB92843298314" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_68553508E2044D02BA01B835AA78D299" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_DCD04C6D920941E49140D5D3BA226CCD" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_CB0BC4621CF04C0BBF889D54B444B476" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_FB0F885DE39248CE8B005E6244D1C7CB" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_05EA7B1C23CF498F80FABCAA6DE60690" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Category Name </td> 
   <td> <p> <img id="image_8C47AD4194424FFB914F54C0126AEF43" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_B5D041A22DFC403C94C72DF5EF08E14F" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_2B941D0DB17A4E7D80B45B8F465029D2" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_43DF1EF23C2B40C18875A18183F5FE8A" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A5AF5ACC34224AE89B62ECFC55598A1B" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_030EDB332C25407AAF6C2513985C341A" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_E240E73760404E16BD2D16F534F17E15" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_9AECEFA8C26B4B0983A147C97C0BB979" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_ECEA5EC6748C42BB8D45E2A92E2E2AF4" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_0AB07EC4A8DD4D779DE98E9390844C8A" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Rank Category Name </td> 
   <td> <p> <img id="image_33D8D6D036BF4B909221E39F82C01A21" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_F207CD0E239D4834A4C6F505F036D841" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_FACCCD4BFBA24D9394B4E0040DD18A20" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_1BB5E96D702A4CF4B0BE823D50E3E65F" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_C632BE62B419464D902A5AB2A318BA0A" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_014FF031A2AA46CABB77F94682FA7A2A" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_7583EB32DB3E4F538F9C917022A9EE3E" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_42124627B05E4FD1B1417728C650E833" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_B43E92367B9D40DFA7C2DBEDF0DF709C" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_6CDA126F236B4040A5C1C56BE0C2909C" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Review Title </td> 
   <td> <p> <img id="image_50BD0F2F2C4F4AFBA89781A7AE171A91" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_53B9B3711C774785B6149B6BD088C112" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_903D16BB646E4A9C98B2B04F0DB6A421" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_B8F0706BCE1A4BCD8760AE10988F9E54" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_0867FAEC30B945ED98228EB1F344D571" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_1ABFB97246ED4E2E9CFD88F0822919FE" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_90BC551172E64D39A87432CFB71FF676" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_212FBB21F4D1499282EAB2B5EC07C6E4" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_2C1506DE4D64409EBD3EF31E6DA485E5" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_C06F1597D1A147E7B7DE53FD90023C57" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Review Comment </td> 
   <td> <p> <img id="image_3B34008198EC4E5EBB55E1B31CD3CBAA" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A5FD916CAA2841039691E70E66D66A2C" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_7883A267FB3C490A89673E5BE6C7EBCE" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A21722AED1564294B9AFE89370756528" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_173ADA32130F40649ED0CD03C7935B91" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_3A30C8104E70445FB5A7BBFAF9E98BEF" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_596819D2B9F24DA1B4312B0E5A5A0728" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_DE6BF1BE82C4429D98FD86D227B0BCB2" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_4EEAD9A625BA4040824D91389E024156" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_A8D01D34BFE1440680019DDC7FCDAA5F" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> App Version </td> 
   <td> <p> <img id="image_71B97577BF154133A0D6DA760626BE33" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_162DCDF090D24B90BC2B0D07121DC7B5" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_E4D34F55823A4E21985E7250C4424F75" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_8E425640005849E78D6C5CFF1063D14C" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_4F49D5079EF342D1B16F739C9D65707C" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_61D143B5D1884CFC90330E70DA904F17" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_E2EDE6E6FA984D1B8CDA06513A08214F" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_2DC925BC1B9B42EBBDA6E47EFB8E09A2" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_3E3B46581CF54715B9003356FA957EF5" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_58044643FFD44CD1A31370F1D41DEEE3" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td> App Store User </td> 
   <td> <p> <img id="image_9B14F4DC100644AFB2BA201C1BD09BD7" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_EDF0CCE6E744429EB5E2C7A0DC8893EC" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_2CCE0C5058BE4919A8FC5989D83D9121" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_01200B415592490F900CD51D0F3BBE10" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_71C2B3965AB74E84AEC719EE2DA2FC12" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_880C04EAC24746CF8B18F3F3D715548E" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_2ABB2BA834A24631B1D865054973C909" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_8C5758B51B654E9BB32F630324012124" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_10827165DACD4B7390754547ED388F4D" src="assets/ClearXRed_Illustrative.png" /> </p> </td> 
   <td> <p> <img id="image_EC1A421DE7FA4069A2D8ED9C8CBA609A" src="assets/AlertApprove_Illustrative.png" /> </p> </td> 
  </tr> 
 </tbody> 
</table>
