---
title: 컴파일러 경고 (수준 1) C4727 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4727
dev_langs:
- C++
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c92e42fe275f821e333a0f04a116034a5bb849a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282784"
---
# <a name="compiler-warning-level-1-c4727"></a>컴파일러 경고(수준 1) C4727
"PCH obj_file_1 및 obj_file_2에 타임 스탬프가 동일한 pch_file를 라는 하는 데 사용 합니다.  첫 번째 PCH를 사용합니다.  
  
 C4727 사용 하 여 여러 번을 컴파일할 때 발생 **/Yc**, 및는 컴파일러에서 모든.obj 파일에 타임 스탬프가 동일한.pch 표시할 수 있습니다.  
  
 컴파일 인 소스 파일 하나를 해결 하려면 **/Yc /c** (pch 생성)를 사용 하 여 별도로 컴파일하고 다른 및 **/Yu /c** (pch 사용) 다음 함께 연결 합니다.  
  
 따라서 다음 않았습니다 고 C4727를 생성 하는 경우:  
  
 **cl /clr /GL a.cpp b.cpp c.cpp /Ycstdafx.h**  
  
 수행한 다음 대신:  
  
 **cl /clr /GL a.cpp /Ycstdafx.h /c**  
  
 **cl /clr /GL b.cpp c.cpp /Yustdafx.h /link a.obj**  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [/Yc(미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu(미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md)