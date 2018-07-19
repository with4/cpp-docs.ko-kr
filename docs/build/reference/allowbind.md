---
title: -ALLOWBIND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af4a9f3d898d0087f0e8e861ccfe72e4adadb1de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368917"
---
# <a name="allowbind"></a>/ALLOWBIND
DLL을 바인딩할 수 있는지 여부를 지정합니다.  
  
```  
  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>설명  
 **/ALLOWBIND** 옵션 비트 이미지를 바인딩해야 허용 되는지 bind.exe 나타내는 DLL의 헤더를 설정 합니다. 바인딩 이미지 로더 다시 지정 하 고 참조 되는 각 DLL에 대 한 수정이 주소를 수행할 필요가 없을 때 더 빠르게 로드를 허용할 수 있습니다. 디지털 서명 된 경우 DLL을 원하지 않을 수 있습니다-바인딩이 서명을 무효화 하므로 합니다. 주소 공간 레이아웃 불규칙화 (ASLR)를 사용 하 여 이미지에 사용 되 면 바인딩에 영향을 주지 않습니다 **/DYNAMICBASE** ASLR을 지 원하는 Windows 버전에 있습니다.  
  
 사용 하 여 **/ALLOWBIND:NO** Bind.exe DLL 바인딩 하지 못하도록 합니다.  
  
 자세한 내용은 참조는 [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) 링커 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)