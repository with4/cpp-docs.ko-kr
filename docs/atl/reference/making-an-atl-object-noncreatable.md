---
title: "ATL 개체를 만들 수 없도록 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 생성할 수 없는 개체"
  - "생성할 수 없는 ATL 개체"
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ATL 개체를 만들 수 없도록 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 기반 COM 개체의 특성을 변경하여 클라이언트에서 직접 개체를 만들 수 없도록 할 수 있습니다.  이런 경우 개체는 직접 만들어지지 않고 다른 개체에 대한 메서드 호출을 통해 반환됩니다.  
  
### 개체를 만들 수 없게 하려면  
  
1.  개체의 [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md)를 제거합니다.  개체를 만들 수 없게 하되 컨트롤은 등록할 수 있게 하려면 OBJECT\_ENTRY\_AUTO를 [OBJECT\_ENTRY\_NON\_CREATEABLE\_EX\_AUTO](../Topic/OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO.md)로 바꿉니다.  
  
2.  .idl 파일의 coclass에 [noncreatable](../../windows/noncreatable.md) 특성을 추가합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    [  
       uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),  
       helpstring("MyObject"),  
      noncreatable  
    ]  
    coclass MyObject  
    {  
       [default] interface IMyInterface;  
    }  
    ```  
  
## 참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+ 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)