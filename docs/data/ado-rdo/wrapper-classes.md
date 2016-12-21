---
title: "래퍼 클래스 | Microsoft Docs"
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
  - "ActiveX 컨트롤[C++], 래퍼 클래스"
  - "데이터 바인딩[C++], ActiveX 컨트롤"
  - "래퍼 클래스[C++], ActiveX 컨트롤"
ms.assetid: ebbc17b9-cc1b-4c29-afa9-da7f9511876e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 래퍼 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 프로젝트에 [컨트롤을 삽입](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)하면 해당 컨트롤의 래퍼 클래스는 기본적으로 포함되지 않습니다.  그러나 [컨트롤의 동작을 수정](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)하려는 경우에는 컨트롤에 대한 래퍼 클래스를 직접 작성할 수 있습니다.  컨트롤을 프로그래밍 방식으로 조작하려는 방법에 따라 컨트롤의 래퍼 클래스를 하나 이상 작성해야 할 경우도 있습니다.  
  
 래퍼 클래스는 컨트롤의 형식 라이브러리\(.tlb\) 파일에 있는 각 coclass에 사용할 수 있습니다.  컨트롤의 래퍼 클래스는 접두사 C가 붙은 컨트롤 이름이어야 합니다.  
  
 래퍼 클래스의 기능에 대한 자세한 내용은 컨트롤의 기본 기술에 대한 개체 모델을 참조하십시오.  
  
 또한 [CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md)을 사용하려면 반환 값을 컨트롤 클래스로 캐스팅해야 하기 때문에 래퍼 클래스가 필요합니다.  예를 들면 다음과 같습니다.  
  
```  
CDBList* pDBList = 0;  
pDBList = static_cast<CDBList*>(GetDlgItem(IDC_DBLIST));  
```  
  
 생성된 .idl 파일을 보면 메서드와 접근자 함수 선언을 직접 볼 수 있을 뿐만 아니라 컨트롤이 노출하는 속성, 메서드 및 이벤트를 확인할 수 있습니다.  컨트롤에서 추가 정보를 보려면 [OLE\/COM 개체 뷰어](../../data/ado-rdo/using-the-ole-com-object-viewer.md)를 사용하십시오.  
  
## 참고 항목  
 [ActiveX 컨트롤 사용](../../data/ado-rdo/using-activex-controls.md)   
 [컨트롤의 런타임 동작 수정](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)