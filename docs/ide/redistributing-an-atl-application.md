---
title: ATL 응용 프로그램 재배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c824dd4ae174a4418c6744e592dd62dc54b9595
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33326386"
---
# <a name="redistributing-an-atl-application"></a>ATL 응용 프로그램 재배포
Visual Studio 2012부터 ATL(액티브 템플릿 라이브러리)은 헤더 전용 라이브러리입니다. ATL 프로젝트에는 ATL에 동적 링크 옵션이 없습니다. 재배포 가능한 ATL 라이브러리가 필요하지 않습니다.  
  
 실행 가능한 ATL 응용 프로그램을 재배포하는 경우 다음 명령을 실행하여 .exe 파일(및 그 안의 모든 컨트롤)을 등록해야 합니다.  
  
```  
filename /regserver  
```  
  
 여기서 `filename`은 실행 파일의 이름입니다.  
  
 Visual Studio 2010에서 MinDependency 또는 MinSize 구성에 대해 ATL 프로젝트를 빌드할 수 있습니다. MinDependency 구성은 **일반** 속성 페이지에서 **ATL 사용** 속성을 **ATL에 정적 링크**로 설정하고 **코드 생성** 속성 페이지(C/C++ 폴더)에서 **런타임 라이브러리** 속성을 **다중 스레드(/MT)** 로 설정하면 사용할 수 있습니다.  
  
 MinSize 구성은 **일반** 속성 페이지에서 **ATL 사용** 속성을 **ATL에 동적 링크**로 설정하고 **코드 생성** 속성 페이지(C/C++ 폴더)에서 **런타임 라이브러리** 속성을 **다중 스레드 DLL(/MD)** 로 설정하면 사용할 수 있습니다.  
  
 MinSize를 사용하면 출력 파일의 크기가 최소화되지만 **다중 스레드 DLL(/MD)** 옵션을 선택한 경우에는 대상 컴퓨터에 ATL100.dll 및 Msvcr100.dll이 있어야 합니다. 모든 ATL 기능을 제공하기 위해 대상 컴퓨터에 ATL100.dll을 등록해야 합니다. ATL100.dll에는 ANSI 및 유니코드 내보내기가 포함되어 있습니다.  
  
 MinDependency 대상에 대한 ATL 또는 OLE DB 템플릿 프로젝트를 빌드하는 경우에는 프로그램 이미지가 커지는 단점은 있지만 대상 컴퓨터에 ATL100.dll을 설치하고 등록하지 않아도 됩니다.  
  
 실행 가능한 ATL 응용 프로그램을 재배포하는 경우 다음 명령을 실행하여 .exe 파일(및 그 안의 모든 컨트롤)을 등록해야 합니다.  
  
```  
filename /regserver  
```  
  
 여기서 `filename`은 실행 파일의 이름입니다.  
  
 OLE DB 템플릿 응용 프로그램의 경우에는 대상 컴퓨터에 최신 버전의 MDAC(Microsoft Data Access Components) 파일이 있어야 합니다. 자세한 내용은 [데이터베이스 지원 파일 재배포](../ide/redistributing-database-support-files.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 파일 재배포](../ide/redistributing-visual-cpp-files.md)