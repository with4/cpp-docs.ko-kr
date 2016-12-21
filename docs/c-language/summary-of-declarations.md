---
title: "선언 요약 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 선언 요약
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`declaration`:  
 *declaration\-specifiers attribute\-seq*  opt *init\-declarator\-list* opt**;**  
  
 \/\* *attribute\-seq*는 Microsoft 전용임 \*\/  
  
 *declaration\-specifiers*:  
 *storage\-class\-specifier declaration\-specifiers* opt  
  
 *type\-specifier declaration\-specifiers* opt  
  
 *type\-qualifier declaration\-specifiers* opt  
  
 *attribute\-seq*:            \/\* *attribute\-seq*는 Microsoft 전용임 \*\/  
 *attribute attribute\-seq* opt  
  
 *attribute*: 다음 중 하나      \/\* Microsoft 전용 \*\/  
 ||||  
|-|-|-|  
|[\_\_asm](../assembler/inline/asm.md)|[\_\_clrcall](../cpp/clrcall.md)|[\_\_stdcall](../cpp/stdcall.md)|  
|[\_\_based](../cpp/based-grammar.md)|[\_\_fastcall](../cpp/fastcall.md)|[\_\_thiscall](../cpp/thiscall.md)|  
|[\_\_cdecl](../cpp/cdecl.md)|[\_\_inline](../misc/inline-inline-forceinline.md)|[\_\_vectorcall](../cpp/vectorcall.md)|  
  
 *init\-declarator\-list*:  
 *init\-declarator*  
  
 *init\-declarator\-list*  **,**  *init\-declarator*  
  
 *init\-declarator*:  
 *declarator*  
  
 *declarator*  **\=**  *initializer* \/\* 스칼라 초기화용 \*\/  
  
 저장소 클래스 지정자:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **형식 정의**  
  
 **\_\_declspec \(**  *extended\-decl\-modifier\-seq*  **\)** \/\* Microsoft 전용 \*\/  
  
 *type\-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 `__int8` \/\* Microsoft 전용 \*\/  
  
 `__int16` \/\* Microsoft 전용 \*\/  
  
 `__int32` \/\* Microsoft 전용 \*\/  
  
 `__int64` \/\* Microsoft 전용 \*\/  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct\-or\-union\-specifier*  
  
 *enum\-specifier*  
  
 *typedef\-name*  
  
 *type\-qualifier*:  
 **const**  
  
 `volatile`  
  
 `declarator`:  
 `pointer` opt *direct\-declarator*  
  
 *direct\-declarator*:  
 *식별자*  
  
 **\(**  *declarator*  **\)**  
  
 *direct\-declarator*  **\[**  *constant\-expression*  opt **\]**  
  
 *direct\-declarator*  **\(**  *parameter\-type\-list*  **\)** \/\* 새로운 스타일의 선언자 \*\/  
  
 *direct\-declarator*  **\(**  *identifier\-list* opt **\)** \/\* 사용되지 않는 스타일의 선언자 \*\/  
  
 `pointer`:  
 **\*** *type\-qualifier\-list* opt  
  
 **\*** *type\-qualifier\-list* opt `pointer`  
  
 *parameter\-type\-list*:                           \/\* 매개 변수 목록 \*\/  
 *parameter\-list*  
  
 *parameter\-list* **, ...**  
  
 *parameter\-list*:  
 *parameter\-declaration*  
  
 *parameter\-list*  **,**  *parameter\-declaration*  
  
 *type\-qualifier\-list*:  
 *type\-qualifier*  
  
 *type\-qualifier\-list type\-qualifier*  
  
 *enum\-specifier*:  
 **enum**  *identifier* opt **{** *enumerator\-list* **}**  
  
 **enum**  *identifier*  
  
 *enumerator\-list*:  
 *enumerator*  
  
 *enumerator\-list*  **,**  `enumerator`  
  
 `enumerator`:  
 *enumeration\-constant*  
  
 *enumeration\-constant*  **\=**  *constant\-expression*  
  
 *enumeration\-constant*:  
 *식별자*  
  
 *struct\-or\-union\-specifier*:  
 *struct\-or\-union identifier* opt **{** *struct\-declaration\-list* **}** *struct\-or\-union identifier*  
  
 *struct\-or\-union*:  
 **struct**  
  
 **union**  
  
 *struct\-declaration\-list*:  
 *struct\-declaration*  
  
 *struct\-declaration\-list struct\-declaration*  
  
 *struct\-declaration*:  
 *specifier\-qualifier\-list struct\-declarator\-list*  **;**  
  
 *specifier\-qualifier\-list*:  
 *type\-specifier specifier\-qualifier\-list* opt  
  
 *type\-qualifier specifier\-qualifier\-list* opt  
  
 *struct\-declarator\-list*:  
 *struct\-declarator struct\-declarator\-list*  **,**  *struct\-declarator*  
  
 *struct\-declarator*:  
 *declarator*  
  
 *type\-specifier declarator* opt **:** *constant\-expression*  
  
 *parameter\-declaration*:  
 *declaration\-specifiers declarator* \/\* 명명된 선언자 \*\/  
  
 *declaration\-specifiers abstract\-declarator* opt **\/\*** 익명 선언자 **\*\/**  
  
 *identifier\-list*: **\/\*** 이전 스타일의 선언자용 **\* \/**  
 *식별자*  
  
 *identifier\-list*  **,**  *identifier*  
  
 *abstract\-declarator*: **\/\*** 익명 선언자와 함께 사용됨 **\*\/**  
 *포인터*  
  
 `pointer` opt *direct\-abstract\-declarator*  
  
 *direct\-abstract\-declarator*:  
 **\(**  *abstract\-declarator*  **\)**  
  
 *direct\-abstract\-declarator* opt **\[** *constant\-expression* opt **\]**  
  
 *direct\-abstract\-declarator* opt **\(** *parameter\-type\-list* opt **\)**  
  
 *initializer*:  
 *인수 식*  
  
 **{**  *initializer\-list*  **}** \/\* 집합체 초기화용 \*\/  
  
 **{**  *initializer\-list*  **, }**  
  
 *initializer\-list*:  
 *initializer*  
  
 *initializer\-list*  **,**  *initializer*  
  
 *type\-name*:  
 *specifier\-qualifier\-list abstract\-declarator* opt  
  
 *typedef\-name*:  
 *식별자*  
  
 *extended\-decl\-modifier\-seq*:\/\*    Microsoft 전용 \*\/  
 *extended\-decl\-modifier* opt  
  
 *extended\-decl\-modifier\-seq extended\-decl\-modifier*  
  
 *extended\-decl\-modifier*:   \/\* Microsoft 전용 \*\/  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
## 참고 항목  
 [호출 규칙](../cpp/calling-conventions.md)   
 [구 구조 문법](../c-language/phrase-structure-grammar.md)   
 [사용되지 않는 호출 규칙](../cpp/obsolete-calling-conventions.md)