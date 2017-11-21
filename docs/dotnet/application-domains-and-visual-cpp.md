---
title: "응용 프로그램 도메인 및 Visual c + + | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 57a45bd6f73040623fe90626b1c3896df3258dd8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="application-domains-and-visual-c"></a>응용 프로그램 도메인 및 Visual C++
있는 경우는 `__clrcall` 가상 함수는 vtable 응용 프로그램 도메인 (appdomain) 됩니다. 하나의 appdomain에 개체를 만들 경우에 해당 appdomain 내에서 가상 함수를 호출할 수 있습니다. 에 정의 된 모든 함수 **/clr: pure** 컴파일 대상 사용는 `__clrcall` 호출 규칙입니다. 따라서에 정의 된 모든 vtable **/clr: pure** 컴파일 대상은 appdomain 별로 지정 됩니다. 혼합 모드에서 (**/clr**) 형식에 있으면 vtable이 프로세스 별로 나면 `__clrcall` 가상 함수입니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [방법: /clr으로 마이그레이션: 순수 (C + + /cli CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>참고 항목  
 [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)