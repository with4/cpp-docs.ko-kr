---
title: "CSyncObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSyncObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSyncObject class"
  - "동기화 클래스, CSyncObject"
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSyncObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

W i n 32의 동기화 개체에 일반적인 기능을 제공 하는 순수 가상 클래스입니다.  
  
## 구문  
  
```  
class CSyncObject : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSyncObject::CSyncObject](../Topic/CSyncObject::CSyncObject.md)|`CSyncObject` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSyncObject::Lock](../Topic/CSyncObject::Lock.md)|동기화 개체에 액세스 합니다.|  
|[CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md)|동기화 개체에 액세스 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CSyncObject::operator HANDLE](../Topic/CSyncObject::operator%20HANDLE.md)|동기화 개체에 대 한 액세스를 제공합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CSyncObject::m\_hObject](../Topic/CSyncObject::m_hObject.md)|내부 동기화 개체 핸들입니다.|  
  
## 설명  
 여러 클래스에서 파생 된 Mfc 라이브러리를 제공 `CSyncObject`.  이러한  [CEvent](../../mfc/reference/cevent-class.md),  [CMutex](../../mfc/reference/cmutex-class.md),  [아니오](../../mfc/reference/ccriticalsection-class.md), 및  [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 동기화 개체를 사용 하는 방법에 대 한 내용은 문서를 참조 하십시오.  [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## 요구 사항  
 **헤더:**  afxmt.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)