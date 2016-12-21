---
title: "CWinFormsControl Class | Microsoft Docs"
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
  - "CWinFormsControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsControl class"
  - "MFC[C++], Windows Forms 지원"
  - "Windows Forms[C++], MFC 지원"
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공 합니다.  
  
## 구문  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### 매개 변수  
 `TManagedControl`  
 MFC 응용 프로그램에서 표시 하는.NET Framework Windows Forms 컨트롤입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWinFormsControl::CWinFormsControl](../Topic/CWinFormsControl::CWinFormsControl.md)|MFC Windows Forms 컨트롤 래퍼 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md)|Windows Forms 컨트롤을 MFC 컨테이너에 만듭니다.|  
|[CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md)|Windows Forms 컨트롤에 대 한 포인터를 검색합니다.|  
|[CWinFormsControl::GetControlHandle](../Topic/CWinFormsControl::GetControlHandle.md)|Windows Forms 컨트롤에 대 한 핸들을 검색합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CWinFormsControl::operator \-\>](../Topic/CWinFormsControl::operator%20-%3E.md)|대체 [CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md) 식에서입니다.|  
|[CWinFormsControl::operator TManagedControl^](../Topic/CWinFormsControl::operator%20TManagedControl%5E.md)|형식에 Windows Forms 컨트롤에 대 한 포인터로 캐스팅합니다.|  
  
## 설명  
 `CWinFormsControl` 클래스를 호스팅하는 Windows Forms 컨트롤의 기본 기능을 제공 합니다.  
  
 Windows Forms을 사용 하 여에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 MFC 코드 창 핸들을 캐시할 수 없습니다 \(일반적으로 저장 `m_hWnd`\).  일부 Windows Forms 컨트롤의 속성에 필요한 기본 Win32 `Window` 멸망 하 고 다시 사용 하 여 `DestroyWindow` 및 `CreateWindow`.  MFC Windows Forms 구현 핸들의 `Destroy` 및 `Create` 이벤트의 컨트롤을 업데이트 하는 `m_hWnd` 멤버.  
  
> [!NOTE]
>  MFC Windows Forms 통합 \(는 AFXDLL 정의\) MFC 동적 링크 프로젝트 에서만 작동 합니다.  
  
## 요구 사항  
 **헤더:** afxwinforms.h  
  
## 참고 항목  
 [CWinFormsDialog Class](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)