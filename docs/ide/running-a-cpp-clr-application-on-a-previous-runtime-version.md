---
title: C + +-clr 응용 프로그램 이전 런타임 버전을 실행 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f8e76930eb9191d27085d92a9d3a678812715fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>이전 버전의 런타임에서 C++ /clr 응용 프로그램 실행
별도로 지정 하지 않으면 컴파일러를 사용 하 여 응용 프로그램을 빌드할 공용 언어 런타임 (CLR) 버전에서 실행 하는 c + +.NET Framework 응용 프로그램이 만들어집니다. 그러나 특정 버전의 런타임을 필수 기능을 제공 하는 다른 모든 버전에서 실행에 대해 작성 하는.exe 응용 프로그램에 대 한 같습니다.  
  
 이를 위해 제공에 런타임 버전 정보를 포함 하는 app.config 파일의 `supportedRuntime` 태그입니다.  
  
 런타임 시 app.config 파일에 이름이 있어야 양식의 *filename.ext*.config, 여기서 *filename.ext* 응용 프로그램을 시작한 실행 파일의 이름이 며와 같은 디렉터리에 있어야 실행 파일입니다. 예를 들어 응용 프로그램 이름이 TestApp.exe, app.config 파일 이름이 TestApp.exe.config 합니다.  
  
 둘 이상의 런타임 버전을 지정 하 고 응용 프로그램이 설치 된 런타임 버전을 둘 이상 있는 컴퓨터에서 실행을 하는 경우 응용 프로그램 구성 파일에 지정 되 고 설치 하는 첫 번째 버전을 사용 합니다.  
  
 자세한 내용은 참조 [하는 방법:.NET Framework 버전을 대상 응용 프로그램 구성](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717)합니다.  
  
 버전 1.0 또는 Visual c + +로 작성 하는 응용 프로그램 CLR의 버전 1.1에서 실행 하려면 컴파일러를 사용 하 여 컴파일된 있어야 [/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)