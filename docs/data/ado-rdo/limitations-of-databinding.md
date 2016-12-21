---
title: "데이터 바인딩의 한계 | Microsoft Docs"
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
  - "데이터 바인딩[C++], Visual C++ 제한 사항"
ms.assetid: 376d7738-5252-4caa-adda-a5486ab2a2a2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 바인딩의 한계
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 바인딩은 데이터 응용 프로그램을 빠르게 만들 수 있는 효과적인 방법입니다.  그러나 현재 데이터 바인딩된 컨트롤의 아키텍처는 두 계층으로 이루어져 있습니다.  
  
## 확장성  
 ADO 데이터 바인딩된 컨트롤은 ADO 데이터 컨트롤의 데이터만 액세스할 수 있습니다.  RDO 데이터 바인딩된 컨트롤은 RDO RemoteData 컨트롤의 데이터만 액세스할 수 있습니다.  RDO RemoteData 컨트롤의 경우 두 계층 아키텍처를 사용하는 것 외에는 다른 방법이 없기 때문에 결과적으로 데이터베이스 서버가 직접 모든 데이터 검색 요청을 받게 됩니다.  데이터베이스 서버에 직접 연결하지 않으려면 중간 계층 비즈니스 개체와 데이터 개체에 대한 액세스를 허용하는 공급자를 작성합니다.  ADO 데이터 컨트롤은 데이터베이스 서버가 아닌 이러한 개체에 연결합니다.  이러한 중간 계층 개체는 COM\+ 1.0 서비스와 같은 트랜잭션 서버에 캐싱하여 관리할 수 있습니다.  
  
## 버전 관리 및 배포  
 컨트롤의 새 버전이 릴리스되면 새 버전으로 응용 프로그램을 테스트해야 합니다.  사용자의 컴퓨터에 다른 응용 프로그램이 설치되어 있고 다른 버전의 컨트롤이 있으면 이 응용 프로그램을 확인해야 합니다.  또한 컨트롤의 새 버전이 릴리스되면 응용 프로그램 사용자에게 새 컨트롤을 배포해야 합니다.  
  
 **드라이버 및 공급자**  
  
 데이터 바인딩은 사용하고 있는 ODBC 드라이버나 OLE DB 공급자만큼 유용합니다.  드라이버와 공급자는 데이터 컨트롤에 데이터를 노출하는 작업을 담당하므로 필요한 기능을 드라이버나 공급자가 지원하는지 반드시 확인해야 합니다.  또한 드라이버나 공급자를 선택하면 사용자가 해당 드라이버나 공급자가 설치했는지 확인해야 합니다.  드라이버나 공급자에 필요한 미들웨어도 설치해야 합니다.  예를 들어, ODBC Oracle에 연결하려면 사용자는 ODBC Oracle 드라이버와 함께 Oracle의 SQL\*Net 미들웨어도 설치해야 합니다.  Oracle 7.3 서버에 연결할 때는 Microsoft Oracle ODBC 드라이버를 사용하는 것이 좋습니다.  
  
 **프로그램 가능성**  
  
 ActiveX 컨트롤은 검정색 상자 모양의 구성 요소로 만들어지므로 프로그램 가능성은 컨트롤의 인터페이스에 대한 개발자의 액세스로 제한됩니다.  리소스 편집기의 데이터 바인딩 모델에서는 ActiveX 컨트롤 삽입 마법사가 생성하는 [래퍼 클래스](../../data/ado-rdo/wrapper-classes.md)를 통해 인터페이스에 대한 액세스가 구현됩니다.  마법사가 coclass를 검색하지 못하면 래퍼 클래스가 생성되지 않으므로 프로그래밍 방식으로 액세스할 수 없습니다.  
  
 이러한 한계가 있지만 데이터 바인딩은 Visual C\+\+를 사용하여 데이터 응용 프로그램을 빠르게 프로토타입화할 수 있는 방법을 제공합니다.  개발 속도가 중요한 경우에는 응용 프로그램을 만들 때 데이터 바인딩을 고려해야 합니다.  
  
## 참고 항목  
 [Visual C\+\+에서 ActiveX 컨트롤을 사용하여 데이터 바인딩](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)