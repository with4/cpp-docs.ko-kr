---
title: "심각한 오류 C1854 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1854
dev_langs:
- C++
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e0a26e902b1a40203bb4323bce8e28e687e9647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1854"></a>심각한 오류 C1854
  
> 미리 컴파일된 헤더를 개체 파일을 만드는 동안 구성 된 정보를 덮어쓸 수 없습니다: '*filename*'  
  
사용자가 지정한는 [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md) 지정은 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 동일한 파일에 대 한 옵션입니다.  
  
이 문제를 해결 하려면 일반적으로 설정 파일을 하나만 사용 하 여 컴파일된 프로젝트에는 **/Yc** 옵션을 사용 하 여 컴파일하는 데 다른 모든 파일 설정의 **/Yu** 옵션입니다. 사용에 대 한 내용은 **/Yc** 옵션과 참조, Visual Studio IDE에서 설정 하는 방법을 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)합니다. 미리 컴파일된 헤더 사용에 대 한 자세한 내용은 참조 하십시오. [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)합니다.  
