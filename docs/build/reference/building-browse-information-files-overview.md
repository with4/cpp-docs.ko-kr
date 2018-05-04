---
title: '찾아보기 정보 파일 빌드: 개요 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2306c69c219320e11259ba6303b76588db8f7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="building-browse-information-files-overview"></a>찾아보기 정보 파일 빌드: 개요
기호 검색에 대 한 찾아보기 정보를 만들려면 컴파일러 BSCMAKE 다음 프로젝트의 각 소스 파일에 대 한.sbr 파일을 만듭니다. EXE 하나의.bsc 파일에.sbr 파일을 연결합니다.  
  
 .Sbr 및.bsc 파일을 생성 이므로 데 시간이 걸립니다 Visual c + + 기본적으로 이러한 함수를 설정 합니다. 현재 정보를 검색 하려는 경우 찾아보기 옵션을 설정 하며 프로젝트를 다시 빌드해야 합니다.  
  
 사용 하 여 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) 또는 [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) .sbr 파일을 만들도록 컴파일러에 지시 합니다. .Bsc 파일을 만들려면 호출할 수 있습니다 [BSCMAKE](../../build/reference/bscmake-command-line.md) 명령줄에서. BSCMAKE를 사용 하 여 명령줄에서에서는 보다 정확 하 게 제어할 수 찾아보기 정보 파일을 조작 합니다. 참조 [BSCMAKE 참조](../../build/reference/bscmake-reference.md) 자세한 정보에 대 한 합니다.  
  
> [!TIP]
>  .Sbr 파일 생성에 선택할 수 있지만.bsc 파일 생성 하도록 둡니다. Fast를 작성은 하지만.bsc 파일 생성에 전원을 켜는 방식으로 프로젝트를 빌드하면 새.bsc 파일을 신속 하 게 만들 수 있습니다를 제공 합니다.  
  
 시간, 메모리 및.bsc 파일의 크기를 줄여.bsc 파일을 빌드하는 데 필요한 디스크 공간을 줄일 수 있습니다.  
  
 참조 [일반 속성 페이지 (프로젝트)](../../ide/general-property-page-project.md) 개발 환경에서 브라우저 파일을 작성 하는 방법에 대 한 내용은 합니다.  
  
### <a name="to-create-a-smaller-bsc-file"></a>더 작은.bsc 파일을 만들려면  
  
1.  사용 하 여 [BSCMAKE 명령줄 옵션](../../build/reference/bscmake-options.md) 찾아보기 정보 파일에서 정보를 제외 합니다.  
  
2.  하나 이상의.sbr 파일 컴파일 또는 어셈블할 때 로컬 기호를 생략 합니다.  
  
3.  개체 파일에 현재 디버깅 단계에 필요한 정보가 없으면 찾아보기 정보 파일을 다시 빌드할 때 BSCMAKE 명령에서 해당.sbr 파일을 생략 합니다.  
  
### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>브라우저 파일 (.bsc)에 있는 여러 프로젝트에서 찾아보기 정보 결합 하려면  
  
1.  중 하나는 프로젝트 수준에서.bsc 파일 빌드 하거나.sbr 파일이 잘리지 않도록 방지 하기 위해 /n 스위치를 사용 하지 마십시오.  
  
2.  모든 프로젝트를 빌드한 후는 입력으로는 모든.sbr 파일이 BSCMAKE를 실행 합니다. 와일드 카드가 허용 됩니다. 예를 들어, 하나의.bsc 파일 모두로 결합할 수 얻게 및.sbr 파일을 사용 하 여 프로젝트 디렉터리 C:\X, C:\Y, 및 C:\Z을 설치한 경우 다음 사용 하 여 BSCMAKE C:\X\\*.sbr C:\Y\\\*.sbr C:\Z\\\*합니다. 결합 된.bsc 파일을 만드는 sbr /o c:\whatever_directory\combined.bsc 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C/c + + 빌드 도구](../../build/reference/c-cpp-build-tools.md)   
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)