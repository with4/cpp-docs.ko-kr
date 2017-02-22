---
title: "CSimpleDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleDialog"
  - "CSimpleDialgo"
  - "CSimpleDialog"
  - "ATL.CSimpleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleDialog class"
  - "CSimpleDialog class, modal dialog boxes in ATL"
  - "대화 상자, 모달"
  - "모달 대화 상자, ATL"
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 기본 모달 대화 상자를 구현합니다.  
  
## 구문  
  
```  
  
      template <  
   WORD t_wDlgTemplateID,  
   BOOL t_bCenter = TRUE  
>  
class CSimpleDialog :  
   public CDialogImplBase  
```  
  
#### 매개 변수  
 *t\_wDlgTemplateID*  
  
 대화 상자 템플릿 리소스의 리소스 ID를 지정 합니다.  
  
 *t\_bCenter*  
 **True 이면** ; 소유자 창에서 가운데에 대화 상자 개체가 있는 경우 그렇지 않으면  **거짓**.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CSimpleDialog::DoModal](../Topic/CSimpleDialog::DoModal.md)|모달 대화 상자를 만듭니다.|  
  
## 설명  
 모달 대화 상자와 기본 기능을 구현 합니다.  `CSimpleDialog`Windows 공용 컨트롤에 대 한만 지원합니다.  만들고 있는 모달 대화 상자를 표시 하려면 대화 상자에 기존 리소스 서식 파일의 이름을 제공 하는이 클래스의 인스턴스를 만듭니다.  미리 정의 된 값 \(예: IDOK 또는 IDCANCEL\) 컨트롤을 클릭할 때 대화 상자 개체를 닫습니다.  
  
 `CSimpleDialog`모달 대화 상자에만 만들 수 있습니다.  `CSimpleDialog`기본 메시지 맵을 사용 하 여 적절 한 처리기 메시지 대화 상자 프로시저를 제공 합니다.  
  
 참조  [대화 상자 구현](../../atl/implementing-a-dialog-box.md) 에 대 한 자세한 내용은.  
  
## 상속 계층 구조  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)