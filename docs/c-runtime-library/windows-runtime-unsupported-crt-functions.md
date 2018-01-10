---
title: "Windows 런타임 지원되지 않는 CRT 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d3e5e2f8ffab670c6e6c5eb95d37b4daced5c6b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Windows 런타임 지원되지 않는 CRT 함수
대부분 CRT(C 런타임) API는 Windows 런타임에서 실행되는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱에서 사용할 수 없습니다. 이들 앱은 /ZW 컴파일러 플래그를 사용하여 빌드합니다. 지원되지 않는 CRT 함수 목록은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
 모든 CRT API는 설명서의 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md) 섹션에서 설명됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)