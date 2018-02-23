---
title: "Windows 런타임 지원되지 않는 CRT 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2f6b06b45da502e3eba898f2907042afeca65c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Windows 런타임 지원되지 않는 CRT 함수
많은 CRT(C 런타임) API는 Windows 런타임에서 실행되는 UWP(유니버설 Windows 플랫폼) 앱에서 사용할 수 없습니다. 이들 앱은 /ZW 컴파일러 플래그를 사용하여 빌드합니다. 지원되지 않는 CRT 함수 목록은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
 모든 CRT API는 설명서의 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md) 섹션에서 설명됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)