---
title: EDITBIN 옵션 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1922e410b0151337ce403e24d20ae90b7e964cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378524"
---
# <a name="editbin-options"></a>EDITBIN 옵션
개체 파일, 실행 파일 및 동적 연결 라이브러리 (Dll)를 수정 하려면 EDITBIN를 사용할 수 있습니다. 옵션에 따라 EDITBIN이 수행하는 변경 사항이 지정됩니다.  
  
 옵션은 옵션 지정자는 대시 (-) 또는 슬래시 (/) 옵션의 이름이 차례로 나옵니다 구성 됩니다. 옵션 이름은 축약 될 수 없습니다. 일부 옵션에는 콜론(:) 다음에 지정된 인수가 사용됩니다. 공백 또는 탭 옵션 사양에 허용 됩니다. 하나 이상의 공백이 나 탭을 사용 하 여 명령줄에서 옵션 사양을 구분 합니다. 옵션 이름 및 해당 키워드 인수 또는 파일 이름 인수는 대/소문자를 구분하지 않습니다. 예를 들어 -bind 및 /BIND는 동일한 항목을 의미합니다.  
  
 EDITBIN에 다음 옵션이 있습니다.  
  
|옵션|용도|  
|------------|-------------|  
|[/ALLOWBIND](../../build/reference/allowbind.md)|DLL을 바인딩할 수 있는지 여부를 지정합니다.|  
|[/ALLOWISOLATION](../../build/reference/allowisolation.md)|DLL 또는 실행 파일 매니페스트 조회 동작을 지정합니다.|  
|[/APPCONTAINER](../../build/reference/appcontainer.md)|앱을 AppContainer 내에서 실행 해야 하는지 여부를 지정 합니다.-예를 들어 UWP 앱.|  
|[/BIND](../../build/reference/bind.md)|로드 시간을 줄이기 위해 지정된 개체에서 진입점에 대한 주소를 설정합니다.|  
|[/DYNAMICBASE](../../build/reference/dynamicbase.md)|로드 시 ASLR(주소 공간 레이아웃 불규칙화)을 사용해서 DLL 또는 실행 가능 이미지를 무작위로 다시 지정할지 여부를 지정합니다.|  
|[/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Microsoft에 내부 오류를 보고합니다.|  
|[/HEAP](../../build/reference/heap.md)|실행 가능 이미지의 힙 크기(바이트)를 설정합니다.|  
|[/HIGHENTROPYVA](../../build/reference/highentropyva.md)|DLL 또는 실행 가능한 이미지가 높은 엔트로피(64비트) ASLR(주소 공간 레이아웃 불규칙화)을 지원하는지 여부를 지정합니다.|  
|[/INTEGRITYCHECK](../../build/reference/integritycheck.md)|로드 시 디지털 서명을 확인할지 여부를 지정합니다.|  
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|개체에서 2GB보다 큰 주소가 지원되는지 여부를 지정합니다.|  
|[/NOLOGO](../../build/reference/nologo-editbin.md)|EDITBIN 시작 배너를 표시하지 않습니다.|  
|[/NXCOMPAT](../../build/reference/nxcompat.md)|실행 가능 이미지가 Windows 데이터 실행 방지와 호환되는지 여부를 지정합니다.|  
|[/REBASE](../../build/reference/rebase.md)|지정된 개체에 대한 기준 주소를 설정합니다.|  
|[/RELEASE](../../build/reference/release.md)|헤더에 체크섬을 설정합니다.|  
|[/ 섹션](../../build/reference/section-editbin.md)|섹션의 특성을 재정의합니다.|  
|[/STACK](../../build/reference/stack.md)|실행 가능 이미지의 스택 크기(바이트)를 설정합니다.|  
|[/SUBSYSTEM](../../build/reference/subsystem.md)|실행 환경을 지정합니다.|  
|[/SWAPRUN](../../build/reference/swaprun.md)|실행 가능 이미지를 스왑 파일에 복사한 후 여기에서 실행해야 하도록 지정합니다.|  
|[/TSAWARE](../../build/reference/tsaware.md)|다중 사용자 환경에서 실행할 수 있도록 응용 프로그램이 설계되도록 지정합니다.|  
|[/VERSION](../../build/reference/version.md)|헤더에서 버전 번호를 설정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C/c + + 빌드 도구](../../build/reference/c-cpp-build-tools.md)   
 [EDITBIN 참조](../../build/reference/editbin-reference.md)