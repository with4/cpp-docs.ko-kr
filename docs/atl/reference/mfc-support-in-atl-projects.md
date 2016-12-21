---
title: "ATL 프로젝트의 MFC 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.atl.addmfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, MFC 지원"
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 프로젝트의 MFC 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 프로젝트 마법사에서 **MFC 지원**을 선택한 경우 ATL 프로젝트는 응용 프로그램을 MFC 응용 프로그램 개체\(클래스\)로 선언합니다.  프로젝트에서는 MFC 라이브러리를 초기화하고 [CWinApp](../../mfc/reference/cwinapp-class.md)에서 파생된 클래스\(*ProjName*\)를 인스턴스화합니다.  
  
 이 옵션은 특성을 사용하지 않는 ATL DLL 프로젝트에만 사용할 수 있습니다.  
  
```  
class CProjNameApp : public CWinApp  
{  
public:  
  
// Overrides  
   virtual BOOL InitInstance();  
   virtual int ExitInstance();  
   DECLARE_MESSAGE_MAP()  
};  
  
BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)  
END_MESSAGE_MAP()  
  
CProjNameApp theApp;  
  
BOOL CProjNameApp::InitInstance()  
{  
   return CWinApp::InitInstance();  
}  
  
int CProjNameApp::ExitInstance()  
{  
   return CWinApp::ExitInstance();  
}  
```  
  
 클래스 뷰에서 응용 프로그램 개체 클래스와 해당 클래스의 `InitInstance` 및 `ExitInstance` 함수를 볼 수 있습니다.  
  
## 참고 항목  
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)