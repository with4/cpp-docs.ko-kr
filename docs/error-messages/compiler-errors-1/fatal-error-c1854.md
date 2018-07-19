---
title: 심각한 오류 C1854 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1854
dev_langs:
- C++
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e517832720e31bfae88e79ad879f1427b9c25a48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230250"
---
# <a name="fatal-error-c1854"></a>심각한 오류 C1854
  
> 미리 컴파일된 헤더를 개체 파일을 만드는 동안 구성 된 정보를 덮어쓸 수 없습니다: '*filename*'  
  
사용자가 지정한는 [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md) 지정은 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 동일한 파일에 대 한 옵션입니다.  
  
이 문제를 해결 하려면 일반적으로 설정 파일을 하나만 사용 하 여 컴파일된 프로젝트에는 **/Yc** 옵션을 사용 하 여 컴파일하는 데 다른 모든 파일 설정의 **/Yu** 옵션입니다. 사용에 대 한 내용은 **/Yc** 옵션과 참조, Visual Studio IDE에서 설정 하는 방법을 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)합니다. 미리 컴파일된 헤더 사용에 대 한 자세한 내용은 참조 하십시오. [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)합니다.  
