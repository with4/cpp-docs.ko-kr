---
title: "CComObjectRoot Class | Microsoft Docs"
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
  - "CComObjectRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot class"
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectRoot Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 typedef의  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 기본 스레딩 모델의 서버에 \(를\) 처리할 수 있습니다.  
  
## 구문  
  
```  
  
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;  
  
```  
  
## 설명  
 `CComObjectRoot`되는 `typedef` 의  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) \(를\) 처리할 기본 스레딩 모델의 서버에.  따라서  [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) 중 하나를 참조  [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx`개체 참조 개수 관리 끌어냅니다 및 집계 된 개체를 처리합니다.  개체가 집계 중인 개체가 집계 중인 경우 마우스 포인터를 알 수 없는 외부 보유 경우 개체 참조 카운트를 보유 합니다.  집계 개체에 대 한 `CComObjectRootEx` 방법을 사용 하 여 내부 개체 생성 하는 오류를 처리 하 고 외부 개체에서 내부 인터페이스 출시 되 면 삭제 하거나 내부 개체를 보호 하기 위해 삭제 됩니다.  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComObjectRootEx Class Members](http://msdn.microsoft.com/ko-kr/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)