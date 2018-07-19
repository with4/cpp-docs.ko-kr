---
title: -vd (생성 치환 비활성화) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vd
dev_langs:
- C++
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6a7b9bacc95c668c1c0f59a3dba172d58c607d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377599"
---
# <a name="vd-disable-construction-displacements"></a>/vd(생성 치환 비활성화)
## <a name="syntax"></a>구문  
  
```  
/vdn  
```  
  
## <a name="arguments"></a>인수  
 `0`  
 Vtordisp 생성자/소멸자 치환 멤버를 표시 하지 않습니다. 모든 클래스 생성자 및 소멸자 호출 가상 없을 경우에이 옵션을 사실상 함수를 선택 합니다.  
  
 `1`  
 숨겨진된 vtordisp 생성자/소멸자 치환 멤버를 작성할을 수 있습니다. 이 선택 항목에는 기본값입니다.  
  
 `2`  
 사용할 수 있습니다 [dynamic_cast Operator](../../cpp/dynamic-cast-operator.md) 생성 중인 개체에 있습니다. 예를 들어 한 dynamic_cast 가상 기본 클래스에서 파생 된 클래스에 있습니다.  
  
 **/vd2** 가상 함수를 사용 하 여 가상 기본을 사용 하는 경우 vtordisp 필드를 추가 합니다. **/vd1** 충분 해야 합니다. 가장 일반적인 사례 **/vd2** 필요는 가상 기본에만 가상 함수는 소멸자가 있는 경우.  
  
## <a name="remarks"></a>설명  
 이러한 옵션은 가상 기본을 사용 하는 c + + 코드에만 적용 됩니다.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 가상 상속 사용 되는 경우 c + + 생성 치환 지원을 구현 합니다. 생성 치환 때 가상 기본에 선언 된 및 파생된 클래스에서 재정의 되는 가상 함수를 생성 하 여 문제가 해결, 추가로 파생된 되는 클래스를 생성 하는 동안에 생성자에서 호출 됩니다.  
  
 이 문제는 가상 함수 전달 될 수 있다는 잘못 된 `this` 포인터 결과적으로 가상 치환 간의 차이점의 기본 클래스와 파생된 된 클래스에 치환입니다. 솔루션에 클래스의 각 가상 기본에 대 한 vtordisp 필드를 호출 하는 단일 생성 치환 조정을 제공 합니다.  
  
 기본적으로는 코드는 사용자 정의 생성자 및 소멸자를 정의 하 고 가상 기본의 가상 함수 때마다 vtordisp 필드 제공 됩니다.  
  
 이러한 옵션에는 전체 소스 파일에 영향을 합니다. 사용 하 여 [vtordisp](../../preprocessor/vtordisp.md) 를 표시 하지 않고 클래스에서 클래스 단위로 vtordisp 필드를 다시 설정 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)