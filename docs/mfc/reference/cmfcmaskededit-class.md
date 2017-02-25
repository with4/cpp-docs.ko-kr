---
title: "CMFCMaskedEdit Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMaskedEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMaskedEdit class"
  - "CMFCMaskedEdit constructor"
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCMaskedEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCMaskedEdit` 클래스는 마스크에 대 한 사용자 입력의 유효성을 검사 하 고 검증된 결과 템플릿에 따라 표시 된 masked edit 컨트롤을 지원 합니다.  
  
## 구문  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|기본 생성자입니다.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCMaskedEdit::DisableMask](../Topic/CMFCMaskedEdit::DisableMask.md)|사용자 입력 유효성 검사를 비활성화 합니다.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableGetMaskedCharsOnly.md)|지정 여부는 `GetWindowText` 메서드는 마스크 된 문자만 검색 합니다.|  
|[CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md)|초기화는 masked 컨트롤 편집.|  
|[CMFCMaskedEdit::EnableSelectByGroup](../Topic/CMFCMaskedEdit::EnableSelectByGroup.md)|Masked edit 컨트롤의 입력, 사용자 또는 모든 사용자 입력의 특정 그룹을 선택할지 여부를 지정 합니다.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableSetMaskedCharsOnly.md)|텍스트에 문자를 마스크에 유효 여부에 대 한 전체 마스크를 지정 합니다.|  
|`CMFCMaskedEdit::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md)|Masked edit 컨트롤에서 텍스트의 유효성을 검색 합니다.|  
|[CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md)|사용자가 입력할 수 있는 유효한 문자의 문자열을 지정 합니다.|  
|[CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md)|Masked edit 컨트롤에 표시 됩니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCMaskedEdit::IsMaskedChar](../Topic/CMFCMaskedEdit::IsMaskedChar.md)|지정 된 문자가 해당 마스크 문자에 대해 유효성을 검사 하는 프레임 워크에서 호출 합니다.|  
  
## 설명  
 사용 하려면 다음 단계를 수행의 `CMFCMaskedEdit` 응용 프로그램에서 제어:  
  
 1.  포함 된 `CMFCMaskedEdit` 창 클래스에 대 한 개체.  
  
 2.  호출 하는 [CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md) 메서드는 마스크를 지정 합니다.  
  
 3.  호출 하는 [CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md) 메서드를 사용할 수 있는 문자 목록을 지정 합니다.  
  
 4.  호출 하는 [CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md) 메서드는 masked 편집 컨트롤에 대 한 기본 텍스트를 지정 합니다.  
  
 5.  호출을 [CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md) 메서드를 유효성 검사 텍스트를 검색 합니다.  
  
 단지 표준 편집 컨트롤의 동작에 따라 마스크, 유효한 문자 및 기본 텍스트를 초기화 하는 하나 이상의 메서드를 호출 하지 않으면 masked edit 컨트롤을 작동 합니다.  
  
## 예제  
 마스크 \(예: 전화 번호\)를 사용 하 여 설정 하는 방법 다음 예제는 `EnableMask` 컨트롤의 masked edit에 대 한 마스크를 만들려면 메서드는 `SetValidChars` 메서드는 사용자가 입력할 수 있는 유효한 문자의 문자열을 지정할 수 및 `SetWindowText` 마스크의 프롬프트를 표시 하는 메서드 편집 컨트롤.  이 이때의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/CPP/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/CPP/cmfcmaskededit-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## 요구 사항  
 **헤더:** afxmaskededit.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)