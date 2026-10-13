# Quickstart for Bitasmbl project (Django)

## 1) Install Bitasmbl-CLI package

```bash
npm i bitasmbl-cli
```

## 2) Run bitasmbl command to set up the project

```bash
bitasmbl pull --repoUrl https://github.com/he1snber8/Bitasmbl_mrdjango_78a_64_51 --appId 64 --repoId 51
```

## 3) Enter into the main directory and start coding!

```bash
cd Bitasmbl_mrdjango_78a_64_51
```

## Customize requirements in a way you like

Bitasmbl organizes development into requirements. Each requirement describes a feature or implementation goal and can define suggested file locations through a `paths` array.

The `paths` property acts as a mapping guideline, helping contributors understand where related code should live.

You can customize `paths` mappings through the `bitasmbl.json` file.

{"Requirement":"Define event booking models","Paths":["**/models.py","**/apps/**/models.py"]}

## Requirement Evaluation

Bitasmbl includes a requirement evaluation workflow that lets contributors select a task and submit work for validation.

Run:

```bash
bitasmbl evaluate
```

Example output:

<pre>
? Available Requirements:

❯ [<span style="color:#9333ea">1</span>] <span style="color:#9333ea"> Define portfolio layout </span>            [3]
  [2] Build showcase components            [3]
  [3] Implement navigation routing         [3]
</pre>

`[x]` on the right represents the number of submission attempts remaining for a requirement.

## Example evaluation result

```py
# ---------------------------------------------------------------------------
# BITASMBL EVALUATION
# ---------------------------------------------------------------------------
# REQUIREMENT:
# Implement product catalog API
#
# SCORE: 17/100
# STATUS: FAIL ✕
#
# INSIGHT:
# The endpoint returns static product data and does not use a model,
# serializer, viewset, filtering, validation, or database persistence.
# ---------------------------------------------------------------------------

from django.http import JsonResponse


def get_products(request):
    products = [
        {
            "id": 1,
            "name": "Keyboard",
            "price": 89.99,
        },
        {
            "id": 2,
            "name": "Mouse",
            "price": 49.99,
        },
    ]

    return JsonResponse(products, safe=False)
```

## Learn More

For complete command references, workflow explanations, and additional documentation, visit:

👉 [Bitasmbl Documentation](https://bitasmbl.com/docs)
