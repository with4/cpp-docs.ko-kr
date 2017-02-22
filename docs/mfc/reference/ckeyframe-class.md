---
title: "CKeyFrame 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CKeyFrame"
  - "CKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyFrame 클래스"
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CKeyFrame 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션 키프레임을 나타냅니다.  
  
## 구문  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CKeyFrame::CKeyFrame](../Topic/CKeyFrame::CKeyFrame.md)|오버로드.  다른 키프레임에 따라 달라지는 키프레임을 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CKeyFrame::AddToStoryboard](../Topic/CKeyFrame::AddToStoryboard.md)|키프레임을 스토리보드에 추가합니다.  \([CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md) 무시.\)|  
|[CKeyFrame::AddToStoryboardAfterTransition](../Topic/CKeyFrame::AddToStoryboardAfterTransition.md)|전환 후에 키프레임을 스토리보드에 추가합니다.|  
|[CKeyFrame::AddToStoryboardAtOffset](../Topic/CKeyFrame::AddToStoryboardAtOffset.md)|오프셋에서 키프레임을 스토리보드에 추가합니다.|  
|[CKeyFrame::GetExistingKeyframe](../Topic/CKeyFrame::GetExistingKeyframe.md)|이 키프레임이 종속되어 있는 키프레임에 대한 포인터를 반환합니다.|  
|[CKeyFrame::GetOffset](../Topic/CKeyFrame::GetOffset.md)|다른 키프레임에서 오프셋을 반환합니다.|  
|[CKeyFrame::GetTransition](../Topic/CKeyFrame::GetTransition.md)|이 키프레임이 종속되어 있는 전환에 대한 포인터를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CKeyFrame::m\_offset](../Topic/CKeyFrame::m_offset.md)|m\_pExistingKeyFrame에 저장된 키프레임에서 이 키프레임의 오프셋을 지정합니다.|  
|[CKeyFrame::m\_pExistingKeyFrame](../Topic/CKeyFrame::m_pExistingKeyFrame.md)|기존 키프레임에 대한 포인터를 저장합니다.  이 키프레임은 기존 키프레임에 대한 m\_offset이 있는 스토리보드에 추가됩니다.|  
|[CKeyFrame::m\_pTransition](../Topic/CKeyFrame::m_pTransition.md)|이 키프레임에서 시작하는 전환에 대한 포인터를 저장합니다.|  
  
## 설명  
 이 클래스는 애니메이션 키프레임을 구현합니다.  키프레임은 스토리보드 내의 한 순간을 나타내며 변환의 시작 시간과 종료 시간을 지정하는 데 사용할 수 있습니다.  키프레임은 다른 키프레임을 기반으로 하고 오프셋\(초 단위\)을 가지거나 전환을 기반으로 하고 이 전환이 끝나는 순간을 나타낼 수 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)