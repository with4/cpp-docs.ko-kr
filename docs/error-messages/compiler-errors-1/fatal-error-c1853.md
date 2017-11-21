---
title: "심각한 오류 C1853 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1853
dev_langs: C++
helpviewer_keywords: C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23b5302428fc216a8349e8cf022c184caa57202c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1853"></a>심각한 오류 C1853
  
> '*filename*' 미리 컴파일된 헤더 파일이 이전 버전의 컴파일러에서 만들어졌거나 미리 컴파일된 헤더는 c + + 고 C에서 (또는 그 반대로) 사용 하는  
  
가능한 원인:  
  
-   미리 컴파일된 헤더는 이전 컴파일러 버전으로 컴파일 되었습니다. 다시 현재 컴파일러로 헤더 컴파일하십시오.  
  
-   미리 컴파일된 헤더는 c + +에서 C로 사용 하기 위해 헤더 중 하나를 지정 하 여이 사용 하 고는 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션 또는 소스 파일의 접미사를 "c"로 변경 합니다. 자세한 내용은 참조 [미리 컴파일 코드에 대 한 두 가지 선택](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code)합니다.