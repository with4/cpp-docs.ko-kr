---
title: "WRL 클래스 라이브러리 프로젝트 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13fc476f696bdd2cb17ed58c496c63747db90322
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wrl-class-library-project-template"></a>WRL 클래스 라이브러리 프로젝트 템플릿
Visual Studio를 사용 하 여 Windows 런타임 c + + 템플릿 라이브러리 (WRL) 프로젝트를 작성 하는 경우 WRL 클래스 라이브러리 프로젝트 템플릿을 다운로드 하 여 작업을 훨씬 간소화할 수 있습니다.  
  
> [!NOTE]
>  기존 프로젝트에 대 한 프로젝트 설정을 수동으로 업데이트 해야 할 경우 참조 [Dll (C + + /cli CX)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx)합니다.  
  
## <a name="download-the-wrl-project-template"></a>WRL 프로젝트 템플릿 다운로드  
 Visual Studio는 Windows 런타임 c + + 템플릿 라이브러리 프로젝트에 대 한 서식 파일을 제공 하지 않습니다. Windows 런타임 c + + 템플릿 라이브러리와 유니버설 Windows 플랫폼 앱에 대 한 기본 클래스 라이브러리를 만드는 프로젝트 템플릿을 다운로드 하는 방법은 다음과 같습니다.  
  
#### <a name="to-download-the-wrl-project-template"></a>WRL 프로젝트 템플릿을 다운로드하려면  
  
1.  메뉴 모음에서 **파일**, **새 프로젝트**합니다.  
  
2.  왼쪽된 창에서는 **새 프로젝트** 대화 상자에서 **온라인**를 선택한 후 **템플릿**합니다.  
  
3.  에 **온라인 템플릿을 검색** 상자 오른쪽 위 모서리를 형식에 `WRL Class Library`합니다. 검색 결과에 템플릿이 나타나면 선택 된 **확인** 단추입니다.  
  
4.  에 **다운로드 및 설치** 조건에 동의 하는 경우 대화 상자를 선택는 **설치** 단추입니다.  
  
5.  템플릿을 설치한 후를 선택 하 여 프로젝트를 만듭니다 **파일**, **새 프로젝트**, 다음을 선택 하 고는 `WRLClassLibrary` 서식 파일입니다. 프로젝트에서 DLL을 만듭니다.  
  
## <a name="examples-that-use-the-project-template"></a>프로젝트 템플릿을 사용하는 예제  
 읽기 [연습: 기본 Windows 런타임 구성 요소 만들기](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) Windows 런타임 구성 요소를 만들려면이 템플릿을 사용 하는 예제에 대 한 합니다.  
  
## <a name="what-the-project-template-provides"></a>프로젝트 템플릿 제공 사항  
 프로젝트 템플릿은 다음을 제공합니다.  
  
-   기본 인터페이스 클래스 구현의 MIDL 특성을 선언하는 .idl 파일 예를 들면 다음과 같습니다.  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   클래스 구현을 정의하는.cpp 파일 예를 들면 다음과 같습니다.  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     [RuntimeClass](../windows/runtimeclass-class.md) 기본 클래스 모듈의 모든 개체의 전역 참조의 관리를 지원 하 고의 메서드는 [IUnknown](http://msdn.microsoft.com/en-us/33f1d79a-33fc-4ce5-a372-e08bda378332) 및 [IInspectable](http://msdn.microsoft.com/en-us/0657e51f-d4c0-46c6-927d-b01e54b6846c) 인터페이스입니다. [InspectableClass](../windows/inspectableclass-macro.md) 매크로 구현 `IUnknown` 및 `IInspectable`합니다. [ActivatableClass](../windows/activatableclass-macros.md) 매크로 클래스의 인스턴스를 만드는 클래스 팩터리를 만듭니다.  
  
-   라이브러리를 정의하는 module.cpp라는 파일은 `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory` 및 `DllGetClassObject`를 내보냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 C++ 템플릿 라이브러리(WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)