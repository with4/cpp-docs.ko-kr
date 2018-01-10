---
title: char, wchar_t, char16_t, char32_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs: C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c01d4718bbc1781ea4705945bb90874384e09058
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
char, wchar_t, char16_t 및 char32_t 형식은 영숫자 문자와 영숫자가 아닌 문자 모양 및 인쇄되지 않는 문자를 나타내는 기본 제공 형식입니다. char은 크기가 8비트이고 wchar_t 및 char16_t는 크기가 16비트이고 char32_t는 32비트입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
char     ch1{ 'a' };    
wchar_t  ch2{ 'a' }; // or {L'a'}    
char16_t ch3{ L'a' };// or {L'a'}    
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## <a name="remarks"></a>설명  
 `char` 형식은 C와 C++의 독창적인 문자 형식이었습니다. ASCII 문자 집합이나 ISO-8859 문자 집합 중 하나 또는 UTF-8  문자 집합의 문자를 저장하는 데 사용할 수 있습니다. 형식 `unsigned char` 나타내는 데는 대개는 *바이트* c + +에는 기본 제공 형식이 아닙니다. char 형식은 다수의 언어에서 텍스트에 적합하지 않습니다. 일반적으로 최신 프로그램에서는 텍스트를 나타내는 데 와이드 문자 형식 중 하나를 사용해야 합니다. 유니코드는  
  
 C++ 표준 라이브러리에서 basic_string 형식은 좁은 문자열과 와이드 문자열 모두에 특화되었습니다. 문자가 char 형식일 때는 std::string을 사용하고, 문자가 wchar_t 형식일 때는 std::wstring을 사용합니다. 텍스트를 나타내는 다른 형식(예: std::stringstream 및 std::cout)들은 좁은 문자열과 와이드 문자열에 대해 특수화되었습니다.  
  
