---
title: "심각한 오류 C1037 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1037
dev_langs:
- C++
helpviewer_keywords:
- C1037
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 892ce10f7d19266ce45d559ce35bc82946887c52
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1037"></a>심각한 오류 C1037
filename 개체 파일을 열 수 없습니다.  
  
 지정 된 개체 파일이 [/Fo](../../build/reference/fo-object-file-name.md) 열 수 없습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  파일 이름이 잘못되었습니다.  
  
2.  메모리가 부족해 파일을 열 수 없습니다.  
  
3.  다른 프로세스에서 파일을 사용 중입니다.  
  
4.  읽기 전용 파일에 동일한 이름이 있습니다.  
  
 Visual C++ .NET(컴파일러 버전 1300)에는 파일 이름(또는 파일 이름에 대한 디렉터리 경로)에 MBCS 문자가 포함된 경우 사용자 로캘을 올바르게 설정해야 하는 버그가 있습니다. 시스템 로캘 설정만으로 충분하지 않습니다. MBCS 문자를 처리하려면 사용자 로캘을 설정해야 합니다.
