---
title: "테스트 컨테이너로 속성 및 이벤트 테스트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX Control Test Container"
  - "ActiveX 컨트롤[C++], 테스트"
  - "ActiveX 컨트롤 디버깅"
  - "속성[MFC], 테스트"
  - "테스트 컨테이너"
  - "테스트, 테스트 컨테이너"
  - "tstcon32.exe"
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 테스트 컨테이너로 속성 및 이벤트 테스트
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The Test Container application, shipped in Visual C\+\+, is an ActiveX control container for testing and debugging ActiveX controls.  Test Container allows the control developer to test the control's functionality by changing its properties, invoking its methods, and firing its events.  Test Container can display logs of data\-binding notifications and also provides facilities for testing an ActiveX control's persistence functionality: you can save properties to a stream or to substorage, reload them, and examine the stored stream data.  This section describes how to use the basic features of Test Container.  For additional information, select the **Help** menu while running Test Container.  
  
### To access the ActiveX Control Test Container  
  
1.  Build the [TSTCON Sample: ActiveX Control Test Container](../top/visual-cpp-samples.md).  
  
### To test your ActiveX control  
  
1.  On the **Edit** menu of Test Container, click **Insert New Control**.  
  
2.  In the **Insert Control** box, select the desired control and click **OK**.  The control will appear in the control container.  
  
    > [!NOTE]
    >  If your control is not listed in the **Insert Control** dialog box, make sure you have registered it with the **Register Controls** command from the **File** menu of Test Container.  
  
 At this point you can test your control's properties or events.  
  
#### To test properties  
  
1.  On the **Control** menu, click **Invoke Methods**.  
  
2.  In the **Method Name** drop\-down list, select the PropPut method for the property you want to test.  
  
3.  Modify the **Parameter Value** or **Parameter Type** and click on the **Set Value** button.  
  
4.  Click **Invoke** to apply the new value to the object.  
  
     The property now contains the new value.  
  
#### To test events and specify the destination of event information.  
  
1.  On the **Options** menu, click **Logging**.  
  
2.  Specify the destination of event information.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [방법: ActiveX 컨트롤 디버깅](../Topic/How%20to:%20Debug%20an%20ActiveX%20Control.md)