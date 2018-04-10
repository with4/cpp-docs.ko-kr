---
title: -CLRTHREADATTRIBUTE (CLR 스레드 특성 설정) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
dev_langs:
- C++
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1aae2dadc2fa7a8c9dc67780bb88b4da60d256e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE(CLR 스레드 특성 설정)
CLR 프로그램의 진입점에 대 한 스레딩 특성을 명시적으로 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### <a name="parameters"></a>매개 변수  
 MTA  
 프로그램의 진입점에 MTAThreadAttribute 특성을 적용합니다.  
  
 없음  
 /CLRTHREADATTRIBUTE를 지정 하지 않으면와 동일 합니다.  CLR 공용 언어 런타임 () 기본 스레딩 특성을 설정할 수 있습니다.  
  
 STA  
 프로그램의 진입점에 STAThreadAttribute 특성을 적용합니다.  
  
## <a name="remarks"></a>설명  
 스레드 특성 설정만 유효.exe를 빌드할 때 주 스레드의 진입점에 영향을 줍니다.  
  
 사용 하는 경우의 기본 진입점 (주 또는 예를 들어 wmain) 지정 스레딩 모델 /CLRTHREADATTRIBUTE를 사용 하 여 하거나 배치 하 여는 스레딩 특성 (STAThreadAttribute 또는 MTAThreadAttribute)을 기본 항목 함수.  
  
 기본이 아닌 진입점을 사용 하 여 /CLRTHREADATTRIBUTE를 사용 하 여 하거나 스레드를 배치 하 여 기본이 아닌 항목 함수에 특성을 다음으로 기본이 아닌 진입점을 지정 하 고 스레딩 모델 지정 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) .  
  
 /CLRTHREADATTRIBUTE로 지정한 스레딩 모델, 소스 코드에서 지정한 스레딩 모델이 일치 하지 않는 경우 링커는 /CLRTHREADATTRIBUTE를 무시 하 고 소스 코드에서 지정한 스레딩 모델을 적용 합니다.  
  
 CLR 프로그램 단일 스레드를 사용 하는 COM 개체를 호스트 하는 경우 예를 들어 단일 스레드를 사용 하는 데 필요한 됩니다.  CLR 다중 스레딩을 사용 하 여를 프로그래밍 하는 경우에 단일 스레드를 사용 하는 COM 개체를 호스팅할 수 없습니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **고급** 속성 페이지.  
  
5.  수정 된 **CLR 스레드 특성** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)