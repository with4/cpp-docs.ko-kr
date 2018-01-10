---
title: "격리 된 응용 프로그램 빌드 C/c + + | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76b0c1fa5b509ae495a12fb63164d7da01f402aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-isolated-applications"></a>C/C++ 격리된 응용 프로그램 빌드
격리 된 응용 프로그램-side-by-side 어셈블리에만 의존 하 고 매니페스트를 사용 하 여 해당 종속성을 바인딩합니다. 완전히 격리 Windows;에서 제대로 실행 되도록 응용 프로그램에 필요 하지 않습니다. 그러나 완전히 격리 된 응용 프로그램을 만드는에 투자를 하 여 나중에 응용 프로그램을 서비스 하는 경우 시간을 절약할 수 있습니다. 완전히 격리 된 응용 프로그램을 만드는의 장점에 자세한 내용은 참조 하십시오. [격리 된 응용 프로그램](http://msdn.microsoft.com/library/aa375190)합니다.  
  
 Visual c + +를 사용 하 여 네이티브 C/c + + 응용 프로그램을 빌드할 때 기본적으로 Visual Studio 프로젝트 시스템에서 Visual c + + 라이브러리 응용 프로그램의 종속성을 설명 하는 매니페스트 파일을 생성 합니다. 경우에 종속 응용 프로그램에 Visual Studio와 함께 다시 빌드하는 즉시에 격리 된 응용 프로그램을 됩니다. 응용 프로그램은 실행 시간에 다른 라이브러리를 사용 하는 경우 해당 라이브러리에 설명 된 단계에 따라 side-by-side-어셈블리를 다시 작성 해야 할 수 있습니다 [C/c + +-side-by-side 어셈블리 빌드](../build/building-c-cpp-side-by-side-assemblies.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [격리 된 응용 프로그램 및 side-by-side-어셈블리의 개념](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)