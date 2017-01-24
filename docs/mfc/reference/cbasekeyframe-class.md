---
title: "CBaseKeyFrame 클래스 | Microsoft Docs"
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
  - "CBaseKeyFrame"
  - "afxanimationcontroller/CBaseKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseKeyFrame 클래스"
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBaseKeyFrame 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

키프레임의 기본 기능을 구현합니다.  
  
## 구문  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CBaseKeyFrame::CBaseKeyFrame](../Topic/CBaseKeyFrame::CBaseKeyFrame.md)|키프레임 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md)|키프레임을 스토리보드에 추가합니다.|  
|[CBaseKeyFrame::GetAnimationKeyframe](../Topic/CBaseKeyFrame::GetAnimationKeyframe.md)|내부 키프레임 값을 반환합니다.|  
|[CBaseKeyFrame::IsAdded](../Topic/CBaseKeyFrame::IsAdded.md)|키프레임이 스토리보드에 추가되었는지 여부를 지정합니다.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](../Topic/CBaseKeyFrame::IsKeyframeAtOffset.md)|오프셋 또는 전환 후에 키프레임을 스토리보드에 추가할지 여부를 지정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CBaseKeyFrame::m\_bAdded](../Topic/CBaseKeyFrame::m_bAdded.md)|키프레임이 스토리보드에 추가되었는지 여부를 지정합니다.|  
|[CBaseKeyFrame::m\_bIsKeyframeAtOffset](../Topic/CBaseKeyFrame::m_bIsKeyframeAtOffset.md)|다른 기존 키프레임의 오프셋에서 또는 일부 전환이 끝날 때 이 키프레임을 스토리보드에 추가해야 하는지 여부를 지정합니다.|  
|[CBaseKeyFrame::m\_keyframe](../Topic/CBaseKeyFrame::m_keyframe.md)|Windows 애니메이션 API 키프레임을 나타냅니다.  키프레임이 초기화되지 않으면 미리 정의된 값 UI\_ANIMATION\_KEYFRAME\_STORYBOARD\_START로 설정됩니다.|  
  
## 설명  
 UI\_ANIMATION\_KEYFRAME 변수를 캡슐화합니다.  키프레임 구현을 위한 기본 클래스로 사용됩니다.  키프레임은 스토리보드 내의 한 순간을 나타내며 변환의 시작 시간과 종료 시간을 지정하는 데 사용할 수 있습니다.  키프레임은 지정된 오프셋\(시간 단위\)에서 스토리보드에 추가된 키프레임 또는 지정된 전환 후에 추가된 키프레임 등 두 가지 형식이 있습니다.  일부 전환 기간은 애니메이션 시작 전에 알 수 없기 때문에 일부 키프레임의 실제 값은 런타임에만 결정됩니다.  키프레임은 전환에 따라 달라질 수 있고 전환 역시 키프레임에 따라 달라질 수 있으므로 키프레임 체인을 만들 때는 무한 재귀를 방지하는 것이 중요합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)