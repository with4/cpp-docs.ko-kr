---
title: "-vmm에서 vm--vmv (일반적인 용도 표시) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vms
- /vmm
- /vmv
dev_langs: C++
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d54ea3cabbbe631006cc22a80fdbf500585ff20f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms, /vmv(일반적인 용도 표시)
경우에 사용 [/vmb, /vmg (표시 메서드)](../../build/reference/vmb-vmg-representation-method.md) 으로 선택한는 [표시 메서드](../../build/reference/vmb-vmg-representation-method.md)합니다. 이러한 옵션 아직 발생 하지 않은 클래스 정의의 상속 모델을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## <a name="remarks"></a>설명  
 다음 표에서는 이러한 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**/vmm**|다중 상속을 사용 하는 것으로 클래스의 멤버에 대 한 포인터의 가장 일반적인 표시를 지정 합니다.<br /><br /> 해당 [상속 키워드](../../cpp/inheritance-keywords.md) 및 인수를 [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) 은 **multiple_inheritance**합니다.<br /><br /> 이 표현은 단일 상속을 위해 필요한 것 보다 큽니다.<br /><br /> 멤버에 대 한 포인터 선언 되는 클래스 정의의 상속 모델이 가상 경우 컴파일러 오류가 발생 합니다.|  
|**/vms**|가장 일반적인 표현은 없습니다 상속 또는 단일 상속을 사용 하는 것으로 클래스의 멤버에 대 한 포인터를 지정 합니다.<br /><br /> 해당 [상속 키워드](../../cpp/inheritance-keywords.md) 및 인수를 [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) 은 **single_inheritance**합니다.<br /><br /> 클래스의 멤버에 대 한 포인터의 가장 작은 가능한 표현을입니다.<br /><br /> 대 멤버에 대 한 포인터를 선언 하는 클래스 정의의 상속 모델은 여러 경우 또는 가상, 컴파일러는 오류를 생성 합니다.|  
|**/vmv**|가상 상속을 사용 하는 것으로 클래스의 멤버에 대 한 포인터의 가장 일반적인 표시를 지정 합니다. 되지 않으며 오류가 발생 하 고 값이 기본값입니다.<br /><br /> 해당 [상속 키워드](../../cpp/inheritance-keywords.md) 및 인수를 [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) 은 **virtual_inheritance**합니다.<br /><br /> 이 옵션에는 큰 포인터와는 다른 옵션 보다 포인터를 해석 하는 추가 코드가 필요 합니다.|  
  
 이 상속 모델 옵션 중 하나를 지정 하면 해당 모델 클래스 다음 상속 유형이 나 전이나는 포인터가 선언 하는지 여부에 관계 없이 클래스 멤버에 대 한 모든 포인터에 사용 됩니다. 따라서 항상 단일 상속 클래스를 사용 하는 경우 크기를 줄입니다 코드 사용 하 여 컴파일하면 **/vms**소비량이 적어지지만 를사용하여컴파일하는가장큰데이터표현이가장일반적인경우를사용하려는경우**/vmv**합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/vmb, /vmg (표시 메서드)](../../build/reference/vmb-vmg-representation-method.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)