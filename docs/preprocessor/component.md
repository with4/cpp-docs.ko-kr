---
title: 구성 요소 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.component
- component_CPP
dev_langs:
- C++
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb453e8fe9d21c25292c4e5f94de90dcc67676a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="component"></a>구성 요소
소스 파일 내에서의 찾아보기 정보 또는 종속성 정보의 수집을 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## <a name="remarks"></a>설명  
  
## <a name="browser"></a>브라우저  
 수집을 설정하거나 해제할 수 있으며 정보가 수집됨에 따라 특정 이름을 무시하도록 지정할 수 있습니다.  
  
 설정 또는 해제를 사용하면 pragma 정방향에서의 찾아보기 정보 컬렉션을 제어합니다. 예:  
  
```  
#pragma component(browser, off)  
```  
  
 컴파일러에서 찾아보기 정보 수집을 중지합니다.  
  
> [!NOTE]
>  이 pragma 사용 하 여 찾아보기 정보 수집을 설정 하려면 [찾아보기 정보를 먼저 활성화 해야](../build/reference/building-browse-information-files-overview.md)합니다.  
  
 **참조** 여부에 관계 없이 옵션을 사용할 수 있습니다는 *이름* 인수입니다. 하지만 사용 하 여 **참조** 없이 *이름* 는 참조 수집을 해제 하거나 (다른 찾아보기 정보가 계속 수집 됨). 예를 들어:  
  
```  
#pragma component(browser, off, references)  
```  
  
 컴파일러에서 참조 정보 수집을 중지합니다.  
  
 사용 하 여 **참조** 와 *이름* 및 **오프** 에 대 한 참조를 방지 *이름* 찾아보기 정보 창에 나타나지 않습니다. 관심 없는 이름 및 형식을 무시하고 찾아보기 정보 파일의 크기를 줄이려면 이 구문을 사용합니다. 예를 들어:  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 에 대 한 참조를 무시 **DWORD** 해당 위치 다음부터 합니다. 에 대 한 참조 수집을 해제할 수 있습니다 `DWORD` 를 사용 하 여 다시 **에**:  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 에 대 한 참조 수집을 다시 시작할 수 있는 유일한 방법은 이것이 *이름*; 명시적으로 설정 해야 모든 *이름* 해제 있다는 합니다.  
  
 전처리기를 확장 하지 않도록 하려면 *이름* (확장 **NULL** 를 **0**), 그 주위에 따옴표를 배치:  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## <a name="minimal-rebuild"></a>최소 다시 빌드  
 Visual C++ 최소 다시 빌드 기능을 사용하려면 컴파일러에서 C++ 클래스 종속성 정보를 만들고 저장해야 합니다. 이러한 작업은 디스크 공간을 사용합니다. 디스크 공간을 절약 하려면 사용할 수 있습니다 `#pragma component( minrebuild, off )` 때마다 종속성 정보를 예를 들어 변하지 않는 헤더 파일에 수집할 필요가 없습니다. 삽입 `#pragma component(minrebuild, on)` 다시 종속성 컬렉션을 설정 하기 위해 변하지 않는 클래스 다음 합니다.  
  
## <a name="reduce-type-information"></a>형식 정보 감소  
 **mintypeinfo** 옵션에 지정 된 영역에 대 한 디버깅 정보가 감소 합니다. 이 정보의 양이 상당하므로 .pdb 및 .obj 파일에 영향을 줍니다. mintypeinfo 영역에서 클래스 및 구조체를 디버깅할 수 없습니다. mintypeinfo 옵션을 사용하면 다음 경고가 발생하지 않도록 하는 데 도움이 될 수 있습니다.  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 자세한 내용은 참조는 [최소 다시 빌드 가능](../build/reference/gm-enable-minimal-rebuild.md) (/ Gm) 컴파일러 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)