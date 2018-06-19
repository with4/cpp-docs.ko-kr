---
title: 컴파일러 오류 C2857 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2857
dev_langs:
- C++
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bb2ec5047646bea420bf109f18a72d87a8f7c44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246349"
---
# <a name="compiler-error-c2857"></a>컴파일러 오류 C2857
' #include ' 문이 /Ycfilename 명령줄 옵션에 지정 된 소스 파일에서 찾을 수 없습니다  
  
 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 옵션 컴파일 중인 소스 파일에 포함 되지 않은 포함 파일의 이름을 지정 합니다.  
  
 이 오류를 때문일 수 있습니다는 `#include` 컴파일되지 않은 조건부 컴파일 블록의 문을 합니다.