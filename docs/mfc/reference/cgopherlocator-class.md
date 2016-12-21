---
title: "CGopherLocator Class | Microsoft Docs"
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
  - "CGopherLocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherLocator class"
  - "gopher locator"
  - "인터넷, gopher searches"
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherLocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gopher "로케이터 항목" gopher 서버에서 가져옵니다 로케이터의 형식을 결정 하 고 로케이터를 사용할 수 있습니다  [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  클래스는 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 Windows XP 플랫폼에서 실행 되지 않지만 이전 플랫폼에서 작업을 계속할 수 있기 때문에 해당 멤버가 되지.  
  
## 구문  
  
```  
class CGopherLocator : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CGopherLocator::CGopherLocator](../Topic/CGopherLocator::CGopherLocator.md)|`CGopherLocator` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CGopherLocator::GetLocatorType](../Topic/CGopherLocator::GetLocatorType.md)|Gopher 로케이터를 구문 분석 하 고 해당 특성을 결정 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CGopherLocator::operator LPCTSTR](../Topic/CGopherLocator::operator%20LPCTSTR.md)|저장 된 문자를 직접 액세스 하는 `CGopherLocator` 개체를 C 스타일 문자열로.|  
  
## 설명  
 해당 서버에서 정보를 검색 하기 전에 응용 프로그램은 gopher 서버 로케이터를 가져와야 합니다.  로케이터 면 해당 로케이터는 불투명 한 토큰으로 취급 해야 합니다.  
  
 Gopher 로케이터 각 파일 또는 서버를 찾을 수 있는 유형을 결정 하는 특성을 가집니다.  참조  [GetLocatorType](../Topic/CGopherLocator::GetLocatorType.md) gopher 로케이터 유형의 목록입니다.  
  
 응용 프로그램이에 대 한 호출을 정상적으로 로케이터를 사용  [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md) 특정 부분의 정보를 검색 합니다.  
  
 방법에 대 한 자세한 내용은 `CGopherLocator` 다른 인터넷 MFC 클래스 사용 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)