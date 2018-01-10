---
title: "Visual Studio 2015와 Visual Studio 2017 간의 C++ 이진 호환성 | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d527a4e0647fe0e8471e168841a93512f4d1a9e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015와 Visual Studio 2017 간의 C++ 이진 호환성


이전 버전의 Visual Studio에서는 여러 버전의 컴파일러 도구 집합 및 런타임 라이브러리를 사용하여 빌드된 개체 파일(OBJ), 정적 라이브러리(LIB), 동적 라이브러리(DLL) 및 실행 파일(EXE) 간의 이진 호환성이 보장되지 않았습니다. Visual Studio 2017에서는 이러한 부분이 변경되었습니다. Visual Studio 2015 및 Visual Studio 2017에서는 C++ 도구 집합 주 번호는 14입니다(Visual Studio 2015의 경우 v140, Visual Studio 2017의 경우 v141). 이는 둘 중 한 버전의 컴파일러를 사용하여 컴파일된 런타임 라이브러리와 응용 프로그램은 대부분 이진 호환성이 보장됨을 나타냅니다. 즉, 예를 들어 Visual Studio 2017에서 DLL을 만들고 Visual Studio 2015를 사용하여 컴파일된 응용 프로그램에서 사용하거나 2015 도구 집합을 사용하여 빌드한 응용 프로그램에서 Visual Studio 2017 재배포 가능 라이브러리를 사용할 수 있습니다.  

이 규칙에는 두 가지 예외 사항이 있습니다. 이러한 경우 이진 호환성이 보장되지 않습니다.  

1) 정적 라이브러리 또는 개체 파일이 /GL 컴파일러 스위치를 사용하여 컴파일된 경우.  

2) 응용 프로그램에서 사용하는 재배포 가능 라이브러리의 버전 번호가 해당 응용 프로그램을 컴파일하는 데 사용된 도구 집합보다 작을 경우. 즉, 플랫폼 도구 집합 v141을 사용하여 프로그램을 컴파일하는 경우 응용 프로그램에서 사용하는 모든 재배포 가능 라이브러리는 v141 이상으로 컴파일되어야 합니다.  

## <a name="see-also"></a>참고 항목  

[Visual C++ 변경 기록](..\porting\visual-cpp-change-history-2003-2015.md)


