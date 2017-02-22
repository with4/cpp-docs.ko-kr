---
title: "CMFCAcceleratorKey Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCAcceleratorKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAcceleratorKey class"
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCAcceleratorKey Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가상 키 매핑 및 서식을 구현 하는 도우미 클래스입니다.  
  
## 구문  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](../Topic/CMFCAcceleratorKey::CMFCAcceleratorKey.md)|`CMFCAcceleratorKey` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCAcceleratorKey::Format](../Topic/CMFCAcceleratorKey::Format.md)|가속도 구조를 시각적으로 변환합니다.|  
|[CMFCAcceleratorKey::SetAccelerator](../Topic/CMFCAcceleratorKey::SetAccelerator.md)|바로 가기 키를 설정 하는 `CMFCAcceleratorKey` 개체입니다.|  
  
## 설명  
 액셀러레이터 키를 바로 가기 키 라고도 합니다.  사용자 입력, 바로 가기 키를 표시 하는 경우는 [CMFCAcceleratorKeyAssignCtrl Class](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 맵 바로 가기 키, Alt \+ Shift \+ S 등 "Alt \+ Shift \+ S"와 같은 사용자 지정 텍스트 형식으로 합니다.  각 `CMFCAcceleratorKey` 개체를 텍스트 형식으로 단일 바로 가기 키를 매핑합니다.  
  
 액셀러레이터 키 테이블 및 바로 가기 키를 사용 하는 방법에 대 한 자세한 내용은[CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md).  
  
## 예제  
 생성 하는 다음 예제는 `CMFCAcceleratorKey` 개체와 사용 방법의 `Format` 메서드.  
  
 [!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/CPP/cmfcacceleratorkey-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)  
  
## 요구 사항  
 **헤더:** afxacceleratorkey.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)