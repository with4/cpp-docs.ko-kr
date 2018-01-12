---
title: "컴파일러 경고 (수준 1) C4727 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4727
dev_langs: C++
helpviewer_keywords: C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 813c2ab18cc81c4477ae094e6c2aa771e3135b7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
  
-   [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md)