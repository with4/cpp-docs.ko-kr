---
title: 응용 프로그램 로컬 폴더에 Visual C++ 응용 프로그램 배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a02e585dc2b82c8b8ad675907e4205db6ad7279
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33337911"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>연습: 응용 프로그램 로컬 폴더에 Visual C++ 응용 프로그램 배포
파일을 폴더에 복사하여 Visual C++ 응용 프로그램을 배포하는 방법을 설명합니다.  
  
## <a name="prerequisites"></a>전제 조건  
  
-   Visual Studio가 설치가 설치된 컴퓨터.  
  
-   Visual C++ 라이브러리가 없는 다른 컴퓨터.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>응용 프로그램 로컬 폴더에 응용 프로그램을 배포하려면  
  
1.  [연습: 설치 프로젝트를 사용하여 Visual C++ 응용 프로그램 배포](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)의 단계를 수행하여 MFC 응용 프로그램을 생성하고 구축합니다.  
  
2.  예를 들어, x86 플랫폼 및 유니코드 지원의 경우 적절한 MFC 및 CRT(C 런타임) 라이브러리 파일을 복사하고 \Program Files\Microsoft Visual Studio 10.0\VC\redist\x86\에서 mfc100u.dll 및 msvcr100.dll을 복사한 다음, MFC 프로젝트의 \Release\ 폴더에 붙여 넣습니다. 복사해야 하는 다른 파일에 대한 자세한 내용은 [재배포할 DLL 확인](../ide/determining-which-dlls-to-redistribute.md)을 참조하세요.  
  
3.  Visual C++ 라이브러리가 없는 두 번째 컴퓨터에서 MFC 응용 프로그램을 실행합니다.  
  
    1.  \Release\ 폴더의 내용을 복사하여 두 번째 컴퓨터의 응용 프로그램 폴더에 붙여 넣습니다.  
  
    2.  두 번째 컴퓨터에서 응용 프로그램을 실행합니다.  
  
     Visual C++ 라이브러리를 응용 프로그램 로컬 폴더에서 사용할 수 있으므로 응용 프로그램이 성공적으로 실행됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [배포 예제](../ide/deployment-examples.md)