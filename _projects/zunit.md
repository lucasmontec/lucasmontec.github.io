---
name: ZUnit
type: Tool
featured: true

font_awesome_icon: fa-terminal

one_liner: A Unity automated testing framework that works with asmdef-less projects.

source_code_url: https://gitlab.com/lucasmontec/zunit
source_code_phrase: The source code is avaliable at GitLab.

---

### ZUnit - Testing Framework

Back when unity testing framework was a mess, I made my own. I had some legacy projects that didn't had asmdefs and adding would be a real pain! I needed to add automated unit testing to them still so I created my own testing framework, even with playmode support.

### Examples:

#### Editor Tests

```csharp
﻿using UnityEngine;
using ZUnit;
using ZUnit.Attributes;
using static ZUnit.ZAssert;

public class TestCase
{
    private string a, b;
    
    [BeforeClass]
    public void Prepare()
    {
        Debug.Log("> Before Class");
        a = "test";
        b = "test";
    }
    
    [AfterClass]
    public void TearDown()
    {
        Debug.Log("> After Class");
    }
    
    [Before]
    public void PrepareMethod()
    {
        Debug.Log(">> Before Method");
    }
    
    [After]
    public void TearDownMethod()
    {
        Debug.Log(">> After Method");
    }
    
    [Test]
    public void Test_SomeTest()
    {
        Debug.Log("LOL");
    }
    
    [PlayModeTest]
    public void Test_PlayModeTest()
    {
        Debug.Log("PLAY MODE TEST");
    }
    
    [Test]
    public void Test_Fail()
    {
        Fail();
    }
    
    [Test]
    public void Test_Prepared()
    {
        AreEqual(a, b);
    }
}
```

#### Playmode Tests

```csharp
using System.Collections;
using UnityEngine;
using ZUnit.Attributes;
using static ZUnit.ZAssert;

namespace ZUnit.Examples
{
    public class BehaviourTest : MonoBehaviour
    {
        [PlayModeTest]
        public void Test_PlayModeTest2()
        {
            Debug.Log(transform.position);
        }
        
        [PlayModeTest]
        public IEnumerator Test_CoroutineTest()
        {
            Debug.Log("Started coroutine test");
            yield return new WaitForSeconds(1f);
            Debug.Log("Ended coroutine test");
        }

        [PlayModeTest]
        public IEnumerator Test_CoroutineFailTest()
        {
            yield return new WaitForSeconds(2f);
            Fail();
        }
        
    }
}

```