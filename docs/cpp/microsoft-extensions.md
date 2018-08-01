---
title: Microsoft 확장 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70b1e0e6ef1294ff23952816db6f468022609f4f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408377"
---
# <a name="microsoft-extensions"></a>Microsoft 확장명
*asm 문*:  
 **__asm***어셈블리 명령* **;** 옵트인    
  
 **__asm {***어셈블리 명령 목록***};** 옵트인      
  
 *어셈블리 명령 목록*:  
 *어셈블리 명령* **;** 옵트인  
  
 *어셈블리 명령* **;** *어셈블리 명령 목록* **;** 옵트인  
  
 *ms 한정자 목록*:  
 *ms 한정자 ms 한정자 목록*최적화  
  
 *ms 한정자*:  
 **__cdecl**  
  
 **__fastcall**  
  
 **__stdcall**  
  
 **__syscall** (이후 구현을 위해 예약 됨)  
  
 **__oldcall** (이후 구현을 위해 예약 됨)  
  
 **__unaligned** (이후 구현을 위해 예약 됨)  
  
 *기반 한정자*  
  
 *기반 한정자*:  
 **__based (** *기반으로 형식당* **)**  
  
 *형식 기반*:  
 *name*  