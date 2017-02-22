---
title: "CW2CWEX 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CW2CWEX"
  - "ATL::CW2CWEX"
  - "ATL.CW2CWEX"
  - "ATL.CW2CWEX<t_nBufferLength>"
  - "ATL::CW2CWEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2CWEX 클래스"
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CW2CWEX 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 사용 하 여 문자열 변환 매크로에서 `CW2CTEX` 및 `CT2CWEX`, 및 typedef `CW2W`.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2CWEX  
```  
  
#### 매개 변수  
 `t_nBufferLength`  
 변환 프로세스에서 사용 되는 버퍼의 크기입니다.  기본 길이 128 바이트입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CW2CWEX::CW2CWEX](../Topic/CW2CWEX::CW2CWEX.md)|생성자입니다.|  
|[CW2CWEX::~CW2CWEX](../Topic/CW2CWEX::~CW2CWEX.md)|소멸자|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CW2CWEX::operator LPCWSTR](../Topic/CW2CWEX::operator%20LPCWSTR.md)|변환 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CW2CWEX::m\_psz](../Topic/CW2CWEX::m_psz.md)|소스 문자열을 저장 하는 데이터 멤버입니다.|  
  
## 설명  
 추가 기능이 필요 하지 않으면 사용 `CW2CTEX`, `CT2CWEX`, 또는 `CW2W` 코드에서.  
  
 이 클래스에서 루프를 사용 하는 안전 및 스택 오버플로가 발생 하지 않습니다.  기본적으로 ATL 변환 클래스 및 매크로 변환에 대 한 ANSI 코드 페이지는 현재 스레드를 사용합니다.  
  
 다음 매크로이 클래스에 따라 발생 합니다.  
  
-   `CW2CTEX`  
  
-   `CT2CWEX`  
  
 Typedef 다음이 클래스를 기반으로 합니다.  
  
-   `CW2W`  
  
 이러한 텍스트 변환 매크로 대 한 설명은 참조 하십시오.  [ATL 및 MFC 문자열 변환 매크로](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## 예제  
 참조  [ATL 및 MFC 문자열 변환 매크로](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) 에 이러한 문자열 변환 매크로 사용 하는 예제입니다.  
  
## 요구 사항  
 **헤더:** atlconv.h  
  
## 참고 항목  
 [CA2AEX 클래스](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)   
 [CA2WEX 클래스](../../atl/reference/ca2wex-class.md)   
 [CW2AEX 클래스](../../atl/reference/cw2aex-class.md)   
 [CW2WEX 클래스](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)