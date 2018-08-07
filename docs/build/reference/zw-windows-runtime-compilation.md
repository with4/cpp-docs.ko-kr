---
title: -ZW (Windows 런타임 컴파일) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs:
- C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fce6c6825ed4ae715a2f4cde6b0e1ffa8b3b6733
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380068"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW(Windows Runtime 컴파일)
소스 지원 하기 위해 코드를 컴파일합니다 [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)])을 유니버설 Windows 플랫폼 (UWP) 앱을 만들 수 있도록 합니다.  
  
 사용 하는 경우 **/ZW** 컴파일하려면를 항상 지정 **/EHsc** 도 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
/ZW /EHsc  
/ZW:nostdlib /EHsc  
```  
  
## <a name="arguments"></a>인수  
 nostdlib  
 Platform.winmd, Windows.Foundation.winmd 및 기타 기본 Windows 메타데이터(.winmd) 파일이 컴파일에 자동으로 포함되지 않음을 나타냅니다. 를 대신 사용 해야는 [/FU (Name Forced #using 파일)](../../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션을 명시적으로 Windows 메타 데이터 파일을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 지정 하는 경우는 **/ZW** 옵션을 컴파일러는 이러한 기능을 지원 합니다.  
  
-   필수 메타 데이터 파일, 네임 스페이스, 데이터 형식 및 함수는 Windows 런타임에서 실행 하는 데 필요한 앱입니다.  
  
-   자동 Windows 런타임 개체의 참조 횟수 및 자동 참조 개수가 0이 되는 경우 개체의 제거 합니다.  
  
 Incremental 링커를 사용 하 여.obj 파일에 포함 된 Windows 메타 데이터를 지원 하지 않으므로 **/ZW** 옵션을는 [/Gm (최소 다시 빌드 가능)](../../build/reference/gm-enable-minimal-rebuild.md) 옵션와 호환 되지 않습니다. **/ZW** .  
  
 자세한 내용은 참조 [Visual c + + 언어 참조](../../cppcx/visual-c-language-reference-c-cx.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)