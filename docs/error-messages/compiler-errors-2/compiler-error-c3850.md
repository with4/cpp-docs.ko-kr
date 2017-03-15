---
title: "컴파일러 오류 C3850 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3850"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3850"
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C3850
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'char': 유니버설 문자 이름에 잘못된 문자를 지정했습니다.  
  
 유니버설 문자 이름으로 표시된 문자는 0\-10FFFF 범위에 있는 유효한 유니코드 코드 포인트를 나타내야 합니다. 유니버설 문자 이름은 유니코드 서로게이트 범위 D800\-DFFF 또는 인코딩된 서로게이트 쌍의 값을 포함할 수 없습니다. 컴파일러는 유효한 코드 포인트에서 자동으로 서로게이트 쌍을 생성합니다.  
  
 C로 컴파일된 코드에서 유니버설 문자 이름은 0024\('$'\), 0040\('@'\) 및 0060\('\`'\)을 제외하고 0000\-009F\(포함\) 범위의 문자를 나타낼 수 없습니다.  
  
 C\+\+로 컴파일된 코드에서 유니버설 문자 이름은 문자열 또는 문자 리터럴의 유효한 유니코드 코드 포인트를 모두 사용할 수 있습니다. 리터럴 외부에서 유니버설 문자 이름은 0000\-001F\(포함\) 또는 007F\-009F\(포함\) 범위의 제어 문자나 기본 소스 문자 집합의 멤버를 나타낼 수 없습니다.  자세한 내용은 [문자 집합](../../cpp/character-sets2.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3850을 생성하고 해결 방법을 보여 줍니다.  
  
```cpp  
// C3850.cpp int main() { int \u0019 = 0;   // C3850, not in allowed range for an identifier const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point }  
```