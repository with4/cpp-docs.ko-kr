---
title: 리소스 전용 DLL 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5249f4528038771162bb96b714524ed751ff39a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367549"
---
# <a name="creating-a-resource-only-dll"></a>리소스 전용 DLL 만들기  
  
리소스 전용 DLL은 아이콘, 비트맵, 문자열 및 대화 상자 등의 리소스만 포함 하는 DLL입니다. 리소스 전용 DLL을 사용 하 여이 같은 리소스 집합으로, 여러 프로그램 간에 공유 하는 것이 좋습니다. 여러 언어로 지역화 된 리소스와 응용 프로그램을 제공 하는 좋은 방법 이기도 (참조 [MFC 응용 프로그램의 지역화 된 리소스: 위성 Dll](../build/localized-resources-in-mfc-applications-satellite-dlls.md)).  
  
리소스 전용 DLL을 만들려면 새 Win32 DLL (MFC 이외) 프로젝트를 만들고 프로젝트에 리소스를 추가 합니다.  
  
-   Win32 프로젝트를 선택는 **새 프로젝트** 대화 상자 및 Win32 프로젝트 마법사에서 DLL 프로젝트 형식을 지정 합니다.  
  
-   DLL에 대 한 리소스 (예: 문자열 또는 메뉴)를 포함 하는 새 리소스 스크립트를 만들고.rc 파일을 저장 합니다.  
  
-   에 **프로젝트** 메뉴를 클릭 하 여 **기존 항목 추가**, 한 다음 프로젝트에 새.rc 파일을 삽입 합니다.  
  
-   지정 된 [/NOENTRY](../build/reference/noentry-no-entry-point.md) 링커 옵션입니다. /NOENTRY 링커를에 대 한 참조를 방지 `_main` ; DLL로 리소스 전용 DLL을 만들려면이 옵션은 필요 합니다.  
  
-   DLL을 빌드합니다.  
  
리소스 전용 DLL을 사용 하는 응용 프로그램 호출 해야 [LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) 를 명시적으로 DLL에 연결 합니다. 제네릭 함수를 호출 하는 리소스에 액세스 하려면 `FindResource` 및 `LoadResource`는 모든 종류의 리소스에서 작업 하거나 다음과 같은 리소스 관련 함수 중 하나를 호출 합니다.  
  
-   `FormatMessage`  
  
-   `LoadAccelerators`  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
응용 프로그램 호출 해야 `FreeLibrary` 완료 되 면 리소스를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
  
[리소스 파일 작업](../windows/working-with-resource-files.md)  
[Visual C++의 DLL](../build/dlls-in-visual-cpp.md)