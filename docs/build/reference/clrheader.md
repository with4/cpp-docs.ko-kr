---
title: -CLRHEADER | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5896e12d5e3b3b3984884388d11c6380e900d73d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="clrheader"></a>/CLRHEADER
```  
/CLRHEADER file  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `file`  
 이미지 파일로 사용 하 여 빌드한 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="remarks"></a>설명  
 CLRHEADER 모든 관리 되는 프로그램에서 사용 되는.NET 헤더에 대 한 정보를 표시 합니다. 출력에.NET 헤더와 헤더 섹션을 바이트 단위로 위치와 크기를 보여 줍니다.  
  
 만 [/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은으로 생성 된 파일에서 사용 하기 위해 사용할 수는 [/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션입니다.  
  
 /CLRHEADER /clr으로 컴파일된 파일에 사용 되 면 됩니다는 **헤더 clr:** dumpbin 출력에는 섹션입니다.  값 **플래그** /clr 옵션을 사용 되었음을 나타냅니다.  
  
-   0--/clr (이미지가 네이티브 코드를 포함할 수 있습니다).  
  
 또한 프로그래밍 방식으로 이미지를 공용 언어 런타임에 대해 빌드된 경우 확인할 수 있습니다.  자세한 내용은 참조 [하는 방법: 이미지가 네이티브 인지 CLR 인지 확인](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)합니다.  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 나중 버전의 컴파일러에서 제거 됩니다. C# "순수" 또는 "안전한" 이어야 하는 코드를 이식 해야 합니다. 
  
## <a name="see-also"></a>참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)