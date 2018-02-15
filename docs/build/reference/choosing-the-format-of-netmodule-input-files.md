---
title: "입력 파일.netmodule 형식을 선택 한다는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6b83039a054e19e62cbbe87befbe08dd7997e51
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule 입력 파일 형식 선택
MSIL.obj 파일 (사용 하 여 컴파일된 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)).netmodule 파일을 사용할 수도 있습니다.  .obj 파일에는 메타 데이터 및 네이티브 기호가 포함 되어 있습니다.  .netmodules에는 메타데이터만 포함됩니다.  
  
 /Addmodule 컴파일러 옵션을 통해 다른 Visual Studio 컴파일러에 MSIL.obj 파일을 전달 (하지만.obj 파일 결과 어셈블리의 일부가 되 고 어셈블리와 함께 제공 되어야) 합니다.  예를 들어, Visual C# 및 Visual Basic에는 /addmodule 컴파일러 옵션이 제공 됩니다.  
  
> [!NOTE]
>  대부분의 경우 .net 모듈을 생성한 컴파일로부터 가져온 .obj 파일을 링커에 전달해야 합니다.  .dll 또는 .netmodule MSIL 모듈 파일을 링커에 전달하면 LNK1107이 발생할 수 있습니다.  
  
 소스에서 #include를 통해 참조하는 연결된 .h 파일과 함께 .obj 파일은 C++ 응용 프로그램이 모듈에서 고유 형식을 사용할 수 있도록 허용하며, 반면에 .netmodule 파일에서는 C++ 응용 프로그램이 관리되는 형식만 사용할 수 있습니다.  .Obj 파일을 전달 하려고 하면 #using 네이티브 형식에 대 한 정보는 사용할 수 없습니다. #include.obj 파일의.h 파일 대신 합니다.  
  
 다른 Visual Studio 컴파일러는 모듈에서 관리 되는 형식을 사용할 수 있습니다.  
  
 다음 설명에 따라 Visual C++ 링커에 대한 모듈 입력으로 .netmodule 또는 .obj 파일을 사용해야 하는지 확인합니다.  
  
-   Visual C++ 이외의 Visual Studio 컴파일러로 빌드하는 경우 .netmodule을 생성하고 .netmodule을 링커에 대한 입력으로 사용합니다.  
  
-   Visual C++ 컴파일러를 사용해서 모듈을 생성하는 중이고 모듈이 라이브러리 이외의 다른 항목을 빌드하는 데 사용될 경우, 컴파일러에서 생성된 .obj 파일을 링커에 대한 모듈 입력으로 사용하고, .netmodule 파일은 입력으로 사용하지 않습니다.  
  
-   (관리 되지 않는 한) 네이티브 라이브러리를 작성 하는 모듈, 경우에 모듈의 링커 입력으로.obj 파일을 사용 하 고.lib 라이브러리 파일을 생성 합니다.  
  
-   모듈이 관리되는 라이브러리를 빌드하는 데 사용되고 링커에 대한 모든 모듈 입력을 확인할 수 있는 경우(/clr:safe로 생성), .obj 파일을 링커에 대한 모듈 입력으로 사용하고 .dll(어셈블리) 또는 .netmodule(모듈) 라이브러리 파일을 생성합니다.  
  
-   관리 되는 라이브러리를 작성 하는 모듈을 링커에 대 한 하나 이상의 모듈 입력 정당한 /clr을 사용한 만들어지지 것입니다..obj 파일을 사용 하 여 모듈의 링커 입력으로 및.dll (어셈블리)를 생성 합니다.  (또한 하려는 각 모듈에 대 한.h 파일 제공 라이브러리 구성 요소 모듈에 대 한.obj 파일의 구성 됩니다 라이브러리에서 관리 되는 형식 및 다음 중 원하는 c + + 응용 프로그램은 라이브러리의 네이티브 형식 사용을 노출 하려는 경우 를 사용 하 여 참조 될 수 있으므로 # 소스 코드에서 include).  
  
## <a name="see-also"></a>참고 항목  
 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)