---
title: "응용 프로그램 로컬 폴더에 Visual c + + 응용 프로그램 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba12271fa4614b5ec0c7c70b3a7773152ebfec3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>연습: 응용 프로그램 로컬 폴더에 Visual C++ 응용 프로그램 배포
파일을 폴더에 복사 하 여 Visual c + + 응용 프로그램을 배포 하는 방법에 설명 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
  
-   Visual Studio가 설치 되어 있는 컴퓨터입니다.  
  
-   Visual c + + 라이브러리를 하지 않은 다른 컴퓨터입니다.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>응용 프로그램 로컬 폴더에 응용 프로그램을 배포 하려면  
  
1.  만들기 및 MFC 응용 프로그램의 단계를 수행 하 여 구축 [연습: 설치 프로젝트는 Visual c + + 응용 프로그램 사용 하 여 배포](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)합니다.  
  
2.  적절 한 MFC 및 C 런타임 (CRT) 라이브러리 파일을 복사-예를 들어,는 x86 플랫폼 및 유니코드 지원, 복사 mfc100u.dll 및 msvcr100.dll files\microsoft Visual Studio 10.0\VC\redist\x86\—and에서 후에 붙여 넣습니다의 \Release\ 폴더 MFC 프로젝트입니다. 복사 해야 하는 다른 파일에 대 한 자세한 내용은 참조 하십시오. [재배포할 Dll 확인](../ide/determining-which-dlls-to-redistribute.md)합니다.  
  
3.  Visual c + + 라이브러리를 하지 않은 다른 컴퓨터에서 MFC 응용 프로그램을 실행 합니다.  
  
    1.  \Release\ 폴더의 내용을 복사 하 고 두 번째 컴퓨터에 응용 프로그램 폴더에 붙여 넣습니다.  
  
    2.  두 번째 컴퓨터에 응용 프로그램을 실행 합니다.  
  
     Visual c + + 라이브러리 응용 프로그램 로컬 폴더에 사용할 수 있으므로 응용 프로그램이 성공적으로 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [배포 예제](../ide/deployment-examples.md)