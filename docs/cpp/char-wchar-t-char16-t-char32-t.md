---
title: char, wchar_t, char16_t, char32_t | Microsoft Docs
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs:
- C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dc38eb9742459139747578a8227bdfaee8bb8a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
형식을 **char**, **wchar_t**, **char16_t** 및 **char32_t** 는 영숫자 문자를 나타내는 기본 제공 형식으로 영숫자가 아닌 문자 모양 및 인쇄할 수 없는 문자가 있습니다.

## <a name="syntax"></a>구문

```cpp  
char     ch1{ 'a' };  // or { u8'a' }   
wchar_t  ch2{ L'a' };    
char16_t ch3{ u'a' };    
char32_t ch4{ U'a' };  
```  
  
## <a name="remarks"></a>설명

**char** 형식이 C 및 c + + 원본 문자 형식 되었습니다. 형식 **unsigned char** 나타내는 데는 대개는 *바이트*, c + +에는 기본 제공 형식이 아닙니다. **char** 형식 문자를 ASCII 문자 집합이 나 iso-8859 문자 집합 및 개별 바이트 Shift JIS 등 멀티 바이트 문자 또는 유니코드 문자 집합의 u t F-8 인코딩으로 저장 데 사용할 수 있습니다. 문자열 **char** 유형 이라고 *좁힐* 멀티 바이트 문자를 인코딩하는 데 사용 하는 경우에 문자열입니다. Microsoft 컴파일러에서 **char** 8 비트 형식입니다.

**wchar_t** 형식은 구현에서 정의 된 와이드 문자 형식입니다. Microsoft 컴파일러에서 u t F-16LE로 인코딩된 유니코드를 저장 하는 데 사용 하는 16 비트 와이드 문자를 나타내는 Windows 운영 체제에서 네이티브 문자 형식입니다. C 런타임 UCRT (Universal) 라이브러리 함수 사용의 와이드 문자 버전 **wchar_t** 하 고 해당 포인터 및 배열 매개 변수 및 반환 값으로 마찬가지로 네이티브 Windows API의 와이드 문자 버전입니다.

**char16_t** 및 **char32_t** 형식은 16 비트 및 32 비트 와이드 문자를 각각 나타냅니다. 유니코드에 저장할 수 u t F-16으로 인코드된는 **char16_t** 유형 및 u t F-32에 저장할 수 있는으로 인코딩된 유니코드는 **char32_t** 유형입니다. 이러한 종류의 문자열 및 **wchar_t** 모든 라고 하는 *넓은* 문자열, 종종 용어는 특히이 많이 있지만 **wchar_t** 유형입니다.

C + + 표준 라이브러리에는 `basic_string` 형식 형식이 좁은 문자열과 와이드 문자열에 대해 특수화 합니다. 사용 하 여 `std::string` 문자 형식의 경우 **char**, `std::u16string` 문자 형식의 경우 **char16_t**, `std::u32string` 문자 형식의 경우 **char32_t** , 및 `std::wstring` 문자 형식의 경우 **wchar_t**합니다. 텍스트를 나타내는 다른 형식을 포함 하 여 `std::stringstream` 및 `std::cout` 좁은 문자열과 와이드 문자열에 대해 특수화 되었습니다.  
  
