---
title: -HIGHENTROPYVA (64 비트 ASLR 지원) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de2487cbeff97ded6e95a36393fbbcfbd510e6d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA(64비트 ASLR 지원)
실행 가능 이미지가 높은 엔트로피 64비트 ASLR(Address Space Layout Randomization)을 지원하도록 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>설명  
 기본적으로는 /HIGHENTROPYVA는 64비트 실행 가능 이미지에 대해 설정되며 32비트 실행 가능 이미지에는 적용되지 않습니다. 이 옵션을 사용하도록 설정하려면 /DYNAMICBASE가 설정되어 있어야 합니다.  
  
 /HIGHENTROPYVA는 64비트 주소를 사용하는 ASLR이 지원되는지 여부를 나타내기 위해 .dll 파일 또는 .exe 파일의 헤더를 수정합니다. 실행 파일과 해당 파일이 종속된 모든 모듈에 대해 이 옵션을 설정하면 64비트 ASLR을 지원하는 운영 체제가 64비트 가상 주소 공간에서 임의 주소를 사용하여 로그 시에 실행 가능 이미지의 세그먼트 기준 주소를 다시 지정할 수 있습니다. 이처럼 큰 주소 공간을 사용하는 경우 공격자가 특정 메모리 영역의 위치를 추측하기가 어려워집니다.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **명령줄** 속성 페이지.  
  
5.  **추가 옵션**, 입력 `/HIGHENTROPYVA` 또는 `/HIGHENTROPYVA:NO`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)