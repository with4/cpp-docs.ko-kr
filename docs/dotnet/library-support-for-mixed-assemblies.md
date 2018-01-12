---
title: "혼합형된 어셈블리에 대 한 라이브러리 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b3bc50416eceac64c134a31a4d7384e33db69b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="library-support-for-mixed-assemblies"></a>혼합형 어셈블리에 대한 라이브러리 지원
Visual c + +는 c + + 표준 라이브러리의 공용 런타임 라이브러리 (CRT)의 사용을 지 원하는 ATL 및 MFC를 사용 하 여 컴파일된 응용 프로그램에 대 한 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다. 따라서 이러한 라이브러리를 사용 하 여.NET Framework 기능을 사용 하는 기존 응용 프로그램 수 있습니다.  
  
 이 지원은 다음 새 DLL 및 가져오기 라이브러리를 도입합니다.  
  
-   /Clr을 사용 하 여 컴파일하면 Msvcmrt [d].lib입니다. 혼합형된 어셈블리가 가져오기 라이브러리에 연결 되어 있습니다.  
  
-   Msvcm90.dll [d] 및 [d] Msvcurt.lib /clr을 사용 하 여 컴파일하면: 순수 합니다. DLL은 관리 되는 실행 시간 CRT (C) 지원을 제공 하는 혼합 된 어셈블리 및 전역 어셈블리 캐시 (GAC)에 설치 된 관리 되는 어셈블리의 일부입니다. 순수형 어셈블리 및 링크를이 가져오기 라이브러리 끝 Msvcm90.dll에 바인딩됩니다.  
  
 이 지원을 여러 관련 이점을 제공 합니다.  
  
-   CRT 및 c + + 표준 라이브러리는 혼합형 및 순수형 코드에서 사용할 수 있습니다. CRT 및 제공 하는 c + + 표준 라이브러리는 확인할 수 있습니다. 궁극적으로, 네이티브 코드에서 사용 하 여 통화는 여전히 동일한 CRT 및 c + + 표준 라이브러리에 라우팅됩니다 됩니다.  
  
-   통합 된 예외 처리 혼합 및 순수 이미지를 수정 합니다.  
  
-   혼합 및 순수 이미지에 있는 c + + 변수의 정적 초기화 합니다.  
  
-   관리 되는 코드에서 프로세스별 및 AppDomain 별 변수를 지원 합니다.  
  
-   이 하 버전 Visual Studio 2003에서 컴파일된 혼합된 Dll에 적용 하는 로더 잠금 문제를 해결 합니다.  
  
 또한이 지원을 다음과 같은 제한 사항을 제공합니다.  
  
-   CRT DLL 모델에만 지원 됩니다 (/clr 또는 /clr을 사용 하 여 컴파일된 코드에 대 한 둘 다: 순수).  
  
-   (모든 개체는 순수 이미지에는 순수 해야) 때문 해당 개체는 Visual c + + 라이브러리를 사용 하는 경우에 단일 이미지의 순수 및 혼합 개체를 혼합할 수 없습니다. 이 작업을 수행 하는 경우 링크 타임 오류가 발생 합니다.  
  
 이전 버전에서 실행 되도록 보장 되지는 대로 현재 버전을 공용 언어 런타임 (CLR)를 업데이트 해야 합니다. 이러한 변경 내용으로 작성 된 코드는 CLR 버전에서 실행 되지 것입니다 1.x 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)