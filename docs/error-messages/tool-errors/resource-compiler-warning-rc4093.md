---
title: "리소스 컴파일러 경고 RC4093 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC4093
dev_langs:
- C++
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d21cbba379e72675b8957be58dc712b83673947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4093"></a>리소스 컴파일러 경고 RC4093
비활성 코드의 문자 상수에서 이스케이프 되지 않은 줄 바꿈  
  
 상수 식의 한 `#if`, `#elif`, **#ifdef**, 또는 **#ifndef** 비활성 뒤에 오는 0으로 코드를 평가 하는 전처리기 지시문입니다. 해당 비활성 코드 내에서 줄 바꿈 문자는 작은따옴표 또는 큰따옴표 집합 내에서 표시 되었습니다.  
  
 다음 큰따옴표가 될 때까지 모든 텍스트 문자 상수 속하는 것으로 간주 되었습니다.