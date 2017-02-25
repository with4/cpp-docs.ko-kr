---
title: "CAtlFileMapping Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlFileMapping<T>"
  - "ATL.CAtlFileMapping"
  - "ATL::CAtlFileMapping"
  - "CAtlFileMapping"
  - "ATL.CAtlFileMapping<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMapping class"
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAtlFileMapping Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 메서드를 추가 하는 캐스트 연산자는 메모리 매핑된 파일 나타내는  [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
typename T= char  
>  
class CAtlFileMapping :  
public CAtlFileMappingBase  
```  
  
#### 매개 변수  
 `T`  
 캐스트 연산자를 사용 하는 데이터의 형식입니다.  
  
## Members  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAtlFileMapping::operator T\*](../Topic/CAtlFileMapping::operator%20T*.md)|암시적으로 변환할 수 있도록 `CAtlFileMapping` 개체에 `T`**\***.|  
  
## 설명  
 이 클래스는 단일 캐스트 연산자를 암시적으로 변환할 수 있도록 추가 `CAtlFileMapping` 개체에 `T`**\***.  다른 멤버는 기본 클래스에서 제공 하는  [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## 상속 계층 구조  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## 요구 사항  
 **헤더:** atlfile.h  
  
## 참고 항목  
 [CAtlFileMappingBase Class](../../atl/reference/catlfilemappingbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)