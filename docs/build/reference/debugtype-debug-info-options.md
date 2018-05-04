---
title: -DEBUGTYPE (디버그 정보 옵션) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /debugtype
dev_langs:
- C++
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66868f7648d20b890f3c1e8c40802d77e3af4544
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE(디버그 정보 옵션)
/DEBUGTYPE 옵션은 /DEBUG 옵션으로 생성된 디버깅 정보의 형식을 지정합니다.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## <a name="arguments"></a>인수  
 CV  
 기호, 줄 번호 및 PDB 파일의 기타 개체 컴파일 정보에 대한 디버그 정보를 내보내도록 링커에 지시합니다. 이 옵션은 기본적으로 사용 때 **/debug** 지정 및 **/DEBUGTYPE** 지정 되지 않았습니다.  
  
 PDATA  
 PDB 파일의 디버그 스트림 정보에 .pdata 및 .xdata 항목을 추가하도록 링커에 지시합니다. 이 옵션은 기본적으로 사용 때 모두는 **/debug** 및 **/DRIVER** 옵션을 지정 합니다. 경우 **/DEBUGTYPE:PDATA** 단독으로 지정 된 링커는 PDB 파일에 디버깅 기호 자동으로 포함 합니다. 경우 **/DEBUGTYPE:PDATA, 픽스업** 지정, 링커는 PDB 파일에 디버깅 기호를 포함 하지 않습니다.  
  
 FIXUP  
 PDB 파일의 디버그 스트림 정보에 재배치 테이블 항목을 추가하도록 링커에 지시합니다. 이 옵션은 기본적으로 사용 때 모두는 **/debug** 및 **/profile** 옵션을 지정 합니다. 경우 **/DEBUGTYPE:FIXUP** 또는 **/DEBUGTYPE:FIXUP, PDATA** 지정, 링커는 PDB 파일에 디버깅 기호를 포함 하지 않습니다.  
  
 에 대 한 인수 **/DEBUGTYPE** 쉼표로 구분 하 여 순서에 관계 없이 함께 사용할 수 있습니다. **/DEBUGTYPE** 옵션 및 해당 인수는 대/소문자 구분 하지 않습니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여 **/DEBUGTYPE** 를 디버깅 스트림에 포함 재배치 테이블 데이터 또는.pdata 및.xdata 헤더 정보를 지정 하는 옵션입니다. 그러면 링커는 커널 모드 코드를 중단할 때 커널 디버거에 표시되는 사용자 모드 코드에 대한 정보를 포함할 수 있습니다. 디버깅 기호를 경우 사용할 수 있도록 설정 하려면 **픽스업** 은 포함 지정는 **CV** 인수입니다.  
  
 응용 프로그램에 대 한 일반는 사용자 모드에서 코드를 디버깅 하는 **/DEBUGTYPE** 옵션이 필요 하지 않습니다. 기본적으로 디버깅을 지정 하는 컴파일러 스위치는 다음과 같이 출력 됩니다. ([/Z7, /Zi, /ZI](../../build/reference/z7-zi-zi-debug-information-format.md)) 모든 정보는 데 필요한 Visual Studio에서 디버거를 내보냅니다. 사용 하 여 **/DEBUGTYPE:PDATA** 또는 **/DEBUGTYPE:CV, PDATA, 픽스업** 장치 드라이버용 구성 앱과 같은 사용자 모드 및 커널 모드 구성 요소를 결합 하는 코드를 디버깅 합니다. 커널 모드 디버거에 대 한 자세한 내용은 참조 하세요. [Windows 용 디버깅 도구 (WinDbg, KD, CDB, NTSD)](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## <a name="see-also"></a>참고 항목  
 [/DEBUG (디버깅 정보 생성)](../../build/reference/debug-generate-debug-info.md)   
 [/DRIVER (Windows NT 커널 모드 드라이버)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [/PROFILE (성능 도구 프로파일러)](../../build/reference/profile-performance-tools-profiler.md)   
 [(WinDbg, KD, CDB, NTSD) Windows 용 디버깅 도구](http://go.microsoft.com/fwlink/p?LinkID=285651)