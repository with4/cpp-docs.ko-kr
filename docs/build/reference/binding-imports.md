---
title: 가져오기 바인딩 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7519fb18ac7f24e79a5f7f664cb35f8eb5b3fd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368930"
---
# <a name="binding-imports"></a>가져오기 바인딩
링커의 기본 동작은 지연 로드 된 DLL에 대 한 바인딩 가능한 가져오기 주소 테이블을 만드는 것입니다. 도우미 함수의 호출 하는 대신 바인딩된 정보를 사용 하려고 합니다 DLL에 바인딩된 경우 **GetProcAddress** 각 참조 가져오기. 타임 스탬프 또는 기본 설정된 주소가 일치 하지 않으면 로드 된 DLL의 도우미 함수 것으로 간주 하 바운드 가져오기 주소 테이블 최신이 존재 하지 않는 경우에 따라 진행 됩니다.  
  
 DLL의 지연 로드 가져오기 바인딩 않을 경우 지정 [지연/](../../build/reference/delay-delay-load-import-settings.md): nobind 링커의 명령줄에서 이미지 파일의 공간이 생성된 소모 되는 바인딩된 가져오기 주소 테이블 못합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)