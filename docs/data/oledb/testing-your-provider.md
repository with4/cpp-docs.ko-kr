---
title: "공급자 테스트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 테스트"
  - "공급자 테스트"
  - "테스트, OLE DB 공급자"
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 공급자 테스트
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

공급자를 출시하기 전에 지정된 순서대로 다음 테스트를 수행해야 합니다.  이러한 테스트를 통해 대부분의 사용자가 공급자를 사용할 때 공급자가 제대로 작동하도록 할 수 있습니다.  
  
1.  OLE DB 소비자 템플릿으로 작성한 [소비자](../../data/oledb/creating-an-ole-db-consumer.md) 응용 프로그램을 사용하여 공급자를 테스트합니다.  테스트 소비자는 공급자의 모든 기능 영역\(추가하거나 수정한 모든 코드\)을 다루어야 합니다.  
  
2.  ADO로 작성한 소비자 응용 프로그램을 사용하여 공급자를 테스트합니다.  대부분의 개발자, 특히 Microsoft Visual Basic과 Microsoft C\# 개발자는 소비자 응용 프로그램에 ADO나 ADO.NET을 사용합니다.  테스트 소비자는 공급자의 모든 기능 영역을 다루어야 합니다.  ADO 소비자 응용 프로그램 예제는 [ADO Code Examples in Microsoft Visual Basic](https://msdn.microsoft.com/en-us/library/ms807514.aspx)를 참조하십시오.  
  
3.  ADO 규칙 테스트를 비롯한 OLE DB 규칙 테스트를 실행하여 공급자가 OLE DB 공급자 수준 0 표준을 충족하는지 확인합니다. \(For an explanation of level 0, search for "OLE DB Level 0 Conformance Tests" at [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/?LinkId=121548).  이러한 테스트 및 이와 관련된 설명서는 Data Access SDK의 Visual C\+\+에 포함되어 있습니다.  뿐만 아니라 이 테스트를 하면 다른 [서비스 공급자](../../data/oledb/ole-db-resource-pooling-and-services.md)가 집합적으로 설치되어 있을 때 공급자가 제대로 실행되는지를 확인할 수 있고 속성을 수정하거나 추가할 경우 도움이 됩니다.  규칙 테스트에 대한 자세한 내용은 Visual Studio CD에 있는 Data Access SDK 추가 정보 파일을 참조하십시오.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)