---
title: "CA2WEX 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLCONV/CA2WEX"
  - "ATL.CA2WEX"
  - "ATL.CA2WEX<t_nBufferLength>"
  - "ATL::CA2WEX"
  - "ATL::CA2WEX<t_nBufferLength>"
  - "CA2WEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2WEX 클래스"
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CA2WEX 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 사용 하 여 문자열 변환 매크로에서 `CA2TEX`, `CA2CTEX`, `CT2WEX`, 및 `CT2CWEX`, 및 typedef  **CA2W**.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2WEX  
```  
  
#### 매개 변수  
 `t_nBufferLength`  
 변환 프로세스에서 사용 되는 버퍼의 크기입니다.  기본 길이 128 바이트입니다.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CA2WEX::CA2WEX](../Topic/CA2WEX::CA2WEX.md)|생성자입니다.|  
|[CA2WEX::~CA2WEX](../Topic/CA2WEX::~CA2WEX.md)|소멸자|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CA2WEX::operator LPWSTR](../Topic/CA2WEX::operator%20LPWSTR.md)|변환 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CA2WEX::m\_psz](../Topic/CA2WEX::m_psz.md)|소스 문자열을 저장 하는 데이터 멤버입니다.|  
|[CA2WEX::m\_szBuffer](../Topic/CA2WEX::m_szBuffer.md)|변환 된 문자열을 저장 하는 데 사용 되는 정적 버퍼입니다.|  
  
## 설명  
 추가 기능이 필요 하지 않으면 사용 `CA2TEX`, `CA2CTEX`, `CT2WEX`, `CT2CWEX`, 또는  **CA2W** 코드에서.  
  
 변환의 결과 저장 하는 데 사용 되는 고정 크기 고정 버퍼가이 클래스를 포함 합니다.  정적 버퍼에 비해 너무 큰 경우 결과 클래스를 할당 메모리를 사용 하 여 `malloc`, 개체가 범위를 벗어날 때 메모리를 확보 합니다.  이렇게, 텍스트와 달리 변환 매크로 사용할 이전 버전의 ATL에서이 클래스에 루프를 사용 하는 안전 이며이 스택 오버플로가 발생 하지 않습니다 수 있습니다.  
  
 클래스는 힙 및 실패에 대 한 메모리를 할당 하려고 하면 호출 `AtlThrow` 의 인수를  **E\_OUTOFMEMORY**.  
  
 기본적으로 ATL 변환 클래스 및 매크로 변환에 대 한 ANSI 코드 페이지는 현재 스레드를 사용합니다.  특정 변환에 대 한 동작을 재정의 하려면 클래스의 생성자는 두 번째 매개 변수로 코드 페이지를 지정 합니다.  
  
 다음 매크로이 클래스에 따라 발생 합니다.  
  
-   `CA2TEX`  
  
-   `CA2CTEX`  
  
-   `CT2WEX`  
  
-   `CT2CWEX`  
  
 Typedef 다음이 클래스를 기반으로 합니다.  
  
-   **CA2W**  
  
 이러한 텍스트 변환 매크로 대 한 설명은 참조 하십시오.  [ATL 및 MFC 문자열 변환 매크로](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## 예제  
 참조  [ATL 및 MFC 문자열 변환 매크로](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) 에 이러한 문자열 변환 매크로 사용 하는 예제입니다.  
  
## 요구 사항  
 **헤더:** atlconv.h  
  
## 참고 항목  
 [CA2AEX 클래스](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)   
 [CW2AEX 클래스](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX 클래스](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX 클래스](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)