---
title: "ATL 인코딩 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인코딩"
  - "인코딩, 함수"
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ATL 인코딩 참조
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Atlenc.h에서 찾을 수 있는 코드에서 uuencode, 16 진수, 예: 공통 인터넷 표준의 범위 및 UTF8 인코딩 지원 됩니다.  
  
### 함수  
  
|||  
|-|-|  
|[AtlGetHexValue](../Topic/AtlGetHexValue.md)|숫자의 16 진수 값을 가져오려면이 함수를 호출 합니다.|  
|[AtlHexDecode](../Topic/AtlHexDecode.md)|데이터는 16 진수 텍스트와 같은 이름으로 이전 호출에 의해 인코딩된 문자열을 디코딩합니다  [AtlHexEncode](../Topic/AtlHexEncode.md).|  
|[AtlHexDecodeGetRequiredLength](../Topic/AtlHexDecodeGetRequiredLength.md)|데이터에서 지정한 길이를 16 진수로 인코딩된 문자열을 디코딩된 포함 될 수 있는 버퍼의 바이트에서 크기를 가져오려면이 함수를 호출 합니다.|  
|[AtlHexEncode](../Topic/AtlHexEncode.md)|일부 데이터는 16 진수 텍스트 문자열로 인코딩하는 데이 함수를 호출 합니다.|  
|[AtlHexEncodeGetRequiredLength](../Topic/AtlHexEncodeGetRequiredLength.md)|문자 인코딩 지정 된 크기의 데이터를 문자열에 포함 될 수 있는 버퍼의 크기를 구하려면이 함수를 호출 합니다.|  
|[AtlUnicodeToUTF8](../Topic/AtlUnicodeToUTF8.md)|유니코드 문자열을 u t F\-8로 변환 하려면이 함수를 호출 합니다.|  
|[BEncode](../Topic/BEncode.md)|"B" 인코딩을 사용 하 여 일부 데이터를 변환 하려면이 함수를 호출 합니다.|  
|[BEncodeGetRequiredLength](../Topic/BEncodeGetRequiredLength.md)|문자 인코딩 지정 된 크기의 데이터를 문자열에 포함 될 수 있는 버퍼의 크기를 구하려면이 함수를 호출 합니다.|  
|[EscapeXML](../Topic/EscapeXML.md)|안전 문자도를 XML에서 사용 하기에 안전 하지 않은 문자를 변환 하려면이 함수를 호출 합니다.|  
|[GetExtendedChars](../Topic/GetExtendedChars.md)|확장 문자의 문자열을 가져오려면이 함수를 호출 합니다.|  
|[IsExtendedChar](../Topic/IsExtendedChar.md)|특정된 문자와 확장된 문자 \(32, 126, 않습니다 탭, 줄 바꿈, 캐리지 리턴 보다 큰\) 있는지 확인 하려면이 함수를 호출 합니다.|  
|[QEncode](../Topic/QEncode.md)|"Q" 인코딩을 사용 하 여 일부 데이터를 변환 하려면이 함수를 호출 합니다.|  
|[QEncodeGetRequiredLength](../Topic/QEncodeGetRequiredLength.md)|문자 인코딩 지정 된 크기의 데이터를 문자열에 포함 될 수 있는 버퍼의 크기를 구하려면이 함수를 호출 합니다.|  
|[QPDecode](../Topic/QPDecode.md)|따옴표 붙은 인쇄 가능한 형식 같은 이전 호출에 의해 인코딩된 데이터의 문자열을 디코딩합니다  [QPEncode](../Topic/QPEncode.md).|  
|[QPDecodeGetRequiredLength](../Topic/QPDecodeGetRequiredLength.md)|따옴표 붙은\-인쇄 가능한 인코딩 문자열을 지정한 길이로 디코딩된 데이터를 포함할 수 있는 버퍼의 바이트에서 크기를 가져오려면이 함수를 호출 합니다.|  
|[QPEncode](../Topic/QPEncode.md)|따옴표 붙은 인쇄 가능한 형식에서 일부 데이터를 인코딩하는 데이 함수를 호출 합니다.|  
|[QPEncodeGetRequiredLength](../Topic/QPEncodeGetRequiredLength.md)|문자 인코딩 지정 된 크기의 데이터를 문자열에 포함 될 수 있는 버퍼의 크기를 구하려면이 함수를 호출 합니다.|  
|[UUDecode](../Topic/UUDecode.md)|이전 호출에 의해 같은 uuencoded 된 데이터의 문자열을 디코딩합니다  [UUEncode](../Topic/UUEncode.md).|  
|[UUDecodeGetRequiredLength](../Topic/UUDecodeGetRequiredLength.md)|디코딩할 uuencoded 문자열에서 지정 된 길이 데이터를 포함할 수 있는 버퍼의 바이트에서 크기를 가져오려면이 함수를 호출 합니다.|  
|[UUEncode](../Topic/UUEncode.md)|일부 데이터에 uuencode이이 함수를 호출 합니다.|  
|[UUEncodeGetRequiredLength](../Topic/UUEncodeGetRequiredLength.md)|문자 인코딩 지정 된 크기의 데이터를 문자열에 포함 될 수 있는 버퍼의 크기를 구하려면이 함수를 호출 합니다.|  
  
### 매크로  
  
|||  
|-|-|  
|[ATL\_ESC 플래그](../Topic/ATL_ESC%20Flags.md)|이러한 플래그의 동작을 제어 하는 데 사용 됩니다  [EscapeXML](../Topic/EscapeXML.md).|  
|[ATLSMTP\_QPENCODE 플래그](../Topic/ATLSMTP_QPENCODE%20Flags.md)|인쇄 방법 따옴표 붙은\-가능한 인코딩 이러한 플래그 설명에서 수행 하는 것  [QPEncode](../Topic/QPEncode.md).|  
|[ATLSMTP\_UUENCODE 플래그](../Topic/ATLSMTP_UUENCODE%20Flags.md)|이러한 플래그는 uuencoding을 수행 하는 방법을 설명  [UUEncode](../Topic/UUEncode.md).|  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)