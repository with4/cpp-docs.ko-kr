---
title: "C/c + +-side-by-side 어셈블리 빌드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c54f0e3b8bceff3daa92ecb3e0ee46d7fbeb666
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ side-by-side 어셈블리 빌드
A [side-by-side-어셈블리](http://msdn.microsoft.com/library/windows/desktop/ff951640) 리소스의 컬렉션은-Dll, windows 클래스, COM 서버, 형식 라이브러리 또는 인터페이스 그룹-런타임 시 사용 하도록 응용 프로그램에 사용할 수 있습니다. 어셈블리에 Dll을 다시 패키지의 주요 이점은 동시에 응용 프로그램에서 여러 버전의 어셈블리를 사용할 수 있습니다 및 현재 설치 된 서비스 업데이트가 릴리스되는 어셈블리 수입니다.  
  
 Visual c + + 응용 프로그램에는 하나 또는 여러 Dll 응용 프로그램의 다른 부분에 사용할 수 있습니다. 런타임에 Dll은 주 프로세스에 로드 되 고 필요한 코드가 실행 됩니다. 응용 프로그램은 운영 체제를 다른 종속 Dll 할 로드 되 고 요청된 된 DLL과 함께 로드 하는 기능을 이해, 요청 된 Dll을 찾도록 합니다. Windows 운영 체제 버전에서 Windows XP, Windows Server 2003 및 Windows Vista 보다 이전 운영 체제 로더에 검색 응용 프로그램의 로컬 폴더 또는 시스템 경로에 지정 된 다른 폴더에 종속 Dll에 대 한 합니다. Windows XP, Windows Server 2003 및 Windows Vista, 운영 체제 로더를 사용 하 여 종속 Dll에 대 한 검색할 수도 수는 [매니페스트](http://msdn.microsoft.com/library/windows/desktop/aa375365) 파일 및 이러한 Dll을 포함 하는 side-by-side-어셈블리에 대 한 검색 합니다.  
  
 기본적으로 Visual Studio와 함께 DLL 빌드될 때에 [응용 프로그램 매니페스트](http://msdn.microsoft.com/library/windows/desktop/aa374191) ID가 2 인 RT_MANIFEST 리소스로 포함 합니다. 실행 파일의 경우 처럼이 매니페스트는 다른 어셈블리에서이 DLL의 종속성을 설명합니다. DLL side-by-side-어셈블리의 일부가 아닙니다.이 DLL에 종속 된 응용 프로그램을 로드 하는 대신 운영 체제 로더에 시스템 경로에이 DLL을 찾을 수에 따라 응용 프로그램 매니페스트를 사용 하지 않이 되었다고 가정 합니다.  
  
> [!NOTE]
>  응용 프로그램 매니페스트를 사용 하 여 매니페스트 ID가 2 인 리소스로 포함 하는 DLL에는 것이 유용 합니다. DLL은 런타임에 동적으로 로드 하는 경우 (예를 들어를 사용 하는 [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175) 함수), 운영 체제 로더는 DLL의 매니페스트에 지정 된 종속 어셈블리를 로드 합니다. Dll에 대 한 외부 응용 프로그램 매니페스트는 동안 확인 하지는 `LoadLibrary` 호출 합니다. 매니페스트 포함 되지 않은 경우 로더는 찾지 종속 어셈블리에 실패 하거나 잘못 된 버전의 어셈블리를 로드 시도할 수 있습니다.  
  
 하나 또는 여러 관련 Dll 해당 side-by-side-어셈블리를 재구성할 수 [어셈블리 매니페스트에](http://msdn.microsoft.com/library/windows/desktop/aa374219)를 설명 하는 다른-함께에서 어셈블리의 종속 뿐만 아니라 어셈블리를 형성 하는 파일 어셈블리입니다.  
  
> [!NOTE]
>  포함 된 하나의 DLL을 어셈블리를 전용 어셈블리는 DLL과 같은 이름을 지정 하 고 ID가 1 인 리소스로이 DLL에 어셈블리 매니페스트가 포함 하는 것이 좋습니다. 예를 들어 DLL의 이름이 mylibrary.dll 인 경우 name 특성의 값에 사용 된 \<assemblyIdentity > 매니페스트의 요소 mylibrary 수도 있습니다. 일부 경우에는 확장명이.dll이 아닌 (예를 들어, MFC ActiveX 컨트롤 프로젝트 생성.ocx 라이브러리)은 외부 어셈블리 매니페스트를 만들 수 있습니다. 이 경우 어셈블리 및 매니페스트의 이름 (예: MyAssembly, MyAssembly.manifest, 및 mylibrary.ocx) DLL의 이름과 달라 야 합니다. 그러나 이러한 라이브러리는 extension.dll 있고이 어셈블리의 향후 유지 관리 비용을 줄이기 위해 리소스 매니페스트를 포함 하려면 이름을 바꿀 여전히 좋습니다. 운영 체제 전용 어셈블리를 검색 하는 방법에 대 한 자세한 내용은 참조 [어셈블리 검색 시퀀스](http://msdn.microsoft.com/library/windows/desktop/aa374224)합니다.  
  
 이러한 변경으로 해당 Dll의 배포를 허용할 수 있습니다는 [전용 어셈블리](http://msdn.microsoft.com/library/windows/desktop/aa370850) 또는 응용 프로그램 로컬 폴더에는 [공유 어셈블리](http://msdn.microsoft.com/library/windows/desktop/aa371839) WinSxS 어셈블리 캐시에 있습니다. 몇 가지 단계를이 새로운 어셈블리가; 런타임에 올바르게 동작 하도록 하기 위해 수행 해야 해야 합니다. 에 설명 된 [만들기-side-by-side 어셈블리에 대 한 지침이](http://msdn.microsoft.com/library/windows/desktop/aa375155)합니다. 어셈블리를 올바르게 작성 한 후 중 하나를 공유 또는 전용 어셈블리로 의존 하는 응용 프로그램과 함께 배포할 수 있습니다. 에 설명 된 지침 중 하나 수행 될 수 있습니다-side-by-side 어셈블리는 공유 어셈블리를 설치할 때 [Windows XP에서 Side-by-side-공유에 대 한 Win32 어셈블리 설치](http://msdn.microsoft.com/library/windows/desktop/aa369532) 사용 또는 [병합 모듈](http://msdn.microsoft.com/library/windows/desktop/aa369820). Side-by-side-어셈블리를 전용 어셈블리로 설치할 때 있습니다 복사 하기만 설치 프로세스의 일부로 해당 DLL, 리소스 및 어셈블리 매니페스트 대상 컴퓨터에 응용 프로그램 로컬 폴더를이 어셈블리 수 있는지 확인 합니다. 런타임 시 로더가 찾을 (참조 [어셈블리 검색 시퀀스](http://msdn.microsoft.com/library/windows/desktop/aa374224)). 사용 하는 또 다른 방법은 [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688) 에 설명 된 지침에 따라 [Windows XP에서 응용 프로그램의 개인 사용에 대 한 Win32 어셈블리 설치](http://msdn.microsoft.com/library/windows/desktop/aa369534)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [배포 예제](../ide/deployment-examples.md)   
 [빌드 C/c + + 격리 된 응용 프로그램](../build/building-c-cpp-isolated-applications.md)   
 [C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)