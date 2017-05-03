---
title: "default 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default_CPP"
dev_langs: 
  - "C++"
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# default 네임스페이스
`default` 네임스페이스는 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\)에서 지원되는 기본 제공 형식의 범위를 지정합니다.  
  
## 구문  
  
```  
namespace default;  
```  
  
## 멤버  
 모든 기본 제공 형식은 다음 멤버를 상속합니다.  
  
|||  
|-|-|  
|[default::\(type\_name\)::Equals 메서드](../cppcx/default-type-name-equals-method.md)|지정한 개체와 현재 개체가 같은지 여부를 확인합니다.|  
|[default::\(type\_name\)::GetHashCode 메서드](../cppcx/default-type-name-gethashcode-method.md)|이 인스턴스의 해시 코드를 반환합니다.|  
|[default::\(type\_name\)::GetType 메서드](../cppcx/default-type-name-gettype-method.md)|현재 형식을 나타내는 문자열을 반환합니다.|  
|[default::\(type\_name\)::ToString 메서드](../cppcx/default-type-name-tostring-method.md)|현재 형식을 나타내는 문자열을 반환합니다.|  
  
### 기본 제공 형식  
  
|이름|설명|  
|--------|--------|  
|`char16`|유니코드\(UTF\-16\) 코드 포인트를 나타내는 숫자가 아닌 16비트 값입니다.|  
|`float32`|32비트 IEEE 754 부동 소수점 숫자입니다.|  
|`float64`|64비트 IEEE 754 부동 소수점 숫자입니다.|  
|`int16`|16비트 부호 있는 정수입니다.|  
|`int32`|32비트 부호 있는 정수입니다.|  
|`int64`|64비트 부호 있는 정수입니다.|  
|`int8`|8비트 부호 있는 숫자 값입니다.|  
|`uint16`|16비트 부호 없는 정수입니다.|  
|`uint32`|32비트 부호 없는 정수입니다.|  
|`uint64`|64비트 부호 없는 정수입니다.|  
|`uint8`|8비트 부호 없는 숫자 값입니다.|  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Visual C\+\+ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)