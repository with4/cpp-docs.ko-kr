---
title: "WRL 통합 (C + + /cli CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 859a25f4fc9698899f1139038e161d28da06220e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wrl-integration-ccx"></a>WRL 통합(C++/CX)

WRL 코드와 자유롭게 혼합할 수 [!INCLUDE[cppwrl](includes/cppwrl-md.md)] ([!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]) 코드입니다. 동일한 변환 단위에서 WRL 개체 핸들을 사용 하 여 선언 하는 개체를 사용할 수 있습니다 (`^`) 표기법 및 [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] 스마트 포인터 (`ComPtr<T>`) 표기법입니다. 하지만 반환 값을 직접 처리 해야 및 [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] HRESULT 오류 코드 및 WRL 예외입니다.
  
## <a name="includecppwrlshortincludescppwrl-short-mdmd-development"></a>[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] 개발

작성 하 고 사용 하는 방법에 대 한 자세한 내용은 [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] 구성 요소 참조 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)합니다.

### <a name="example"></a>예

다음 코드 조각 WRL을 사용 하 여 설명 하 고 [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] 를 사용할 [!INCLUDE[wrt](includes/wrt-md.md)] 클래스 및 메타 데이터 파일을 검사 합니다.

예의 코드 조각에서 가져온 것은 [Windows 스토어 앱 포럼 빌드](http://social.msdn.microsoft.com/Forums/winappswithnativecode/thread/211ef583-db11-4e55-926b-6d9ab53dbdb4)합니다. 이 코드 조각의 작성자가 제공한 고지 사항과 조건은 다음과 같습니다.

1. C++는 [!INCLUDE[wrt](includes/wrt-md.md)] 형식에 반영하기 위한 특정 API를 제공하지 않지만 형식에 대한 Windows 메타데이터 파일(.winmd)은 CLR 메타데이터 파일과 완전히 호환됩니다. Windows는 특정 형식에 대한 .winmd 파일을 가져오기 위한 새로운 메타데이터 검색 API(RoGetMetaDataFile)를 제공합니다. 그러나 이러한 API는 C++ 개발자만 사용할 수 있으므로 사용자가 클래스를 인스턴스화할 수 없습니다.

1. 또한 코드가 컴파일되면 Runtimeobject.lib 및 Rometadata.lib를 링커에 전달해야 합니다.

1. 이 조각은 있는 그대로 제공됩니다. 올바르게 작동할 것이라 예상하지만 오류를 포함하고 있을 수 있습니다.

```cpp
#include <hstring.h>
#include <cor.h>
#include <rometadata.h>
#include <rometadataresolution.h>
#include <collection.h>

namespace ABI_Isolation_Workaround {
    #include <inspectable.h>
    #include <WeakReference.h>
}
using namespace ABI_Isolation_Workaround;
#include <wrl/client.h>

using namespace Microsoft::WRL;
using namespace Windows::Foundation::Collections;

IVector<String^>^ GetTypeMethods(Object^);

MainPage::MainPage()
{
    InitializeComponent();

    Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/");
    auto methods = GetTypeMethods(uri);

    std::wstring strMethods;
    std::for_each(begin(methods), end(methods), [&strMethods](String^ methodName) {
        strMethods += methodName->Data();
        strMethods += L"\n";
    });

    wprintf_s(L"%s\n", strMethods.c_str());
}

IVector<String^>^ GetTypeMethods(Object^ instance)
{
    HRESULT hr;
    HSTRING hStringClassName;
    hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ className = reinterpret_cast<String^>(hStringClassName);

    ComPtr<IMetaDataDispenserEx> metadataDispenser; ComPtr<IMetaDataImport2> metadataImport; hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf());
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    HSTRING hStringFileName;
    mdTypeDef typeDefToken;
    hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ fileName = reinterpret_cast<String^>(hStringFileName);

    HCORENUM hCorEnum = 0;
    mdMethodDef methodDefs[2048];
    ULONG countMethodDefs = sizeof(methodDefs);
    hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    wchar_t methodName[1024];
    ULONG countMethodName;
    std::wstring strMethods;
    Vector<String^>^ retVal = ref new Vector<String^>();

    for (int i = 0; i < countMethodDefs; ++i)
    {
        countMethodName = sizeof(methodName);
        hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr);
        if (SUCCEEDED(hr))
        {
            methodName[ countMethodName ] = 0;
            retVal->Append(ref new String(methodName));
        }
    }
    return retVal;
}

```

## <a name="see-also"></a>참고 항목

[다른 언어와의 상호 운용](interoperating-with-other-languages-c-cx.md)  
