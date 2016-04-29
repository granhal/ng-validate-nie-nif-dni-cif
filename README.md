# ng-validate-nie-nif-dni-cif
Module for validate NIE / NIF / DNI and CIF for spanish validations forms

##Requisites:
* Angular 1.0.8+ - https://angularjs.org/

##How to use:
* Install angular in your client
* call ngValidateNIEs.js or ngValidateNIEs.min.js after angular

```html
<script type="text/javascript" src="js/angular.min.js"></script>
<script type="text/javascript" src="js/ngValidateNIEs.min.js"></script>
```

###Inyect dependencies in module
```javascript
var yourApp = angular.module('yourApp', ['ngValidateNIEs']);
```

###In your view insert (is a simple example):
```html
<input type="text" data-ng-model="data.nif" placeholder="DNI/NIF/NIE" validate-ni-es required>
```

###In your view insert (is a example, this example using bootstrap and font-awesome lib's, and others filters):
```html
<form name="signupForm" id="signup-form" data-ng-submit="$close(); processData(data, 3); ">
    <div class="col-md-4">
        <div class="form-group text-center-xs has-feedback">
            <label for="nif-input">DNI/NIF/NIE</label>
            <div class="input-group-info">
                <input type="text" data-ng-model="data.nif" class="form-control text-center" id="nif-input" name="nifInput" placeholder="DNI/NIF/NIE" validate-ni-es required>
                <span class="input-group-btn">
                    <span class="btn btn-default" type="button" data-share-focus tabindex="-1">
                        <!-- This span emulates a button that properly work with shareFocus-->
                        <span class="fa fa-question-circle"></span>
                    </span>
                </span>
            </div>

            <div class="tooltip-info animated flipInX">
                <div data-ng-bind="('VALIDATION.NIF_NIE' | translate)"></div>
                <div data-ng-show="signupForm.nifInput.$dirty && !signupForm.nifInput.$valid" class="error_msg animated fadeIn" data-ng-bind="('VALIDATION.INVALID_NIF_NIE' | translate)"></div>
            </div>

            <span data-ng-show="signupForm.nifInput.$dirty && signupForm.nifInput.$valid" class="fa fa-check form-control-feedback green animated fadeIn" aria-hidden="true"></span>
            <span data-ng-show="signupForm.nifInput.$dirty && !signupForm.nifInput.$valid" class="fa fa-times form-control-feedback red animated fadeIn" aria-hidden="true"></span>
            <span data-ng-show="submitClicked && !signupForm.nifInput.$valid" class="error_msg animated fadeIn" data-ng-bind="validationErrors['nif-input']"></span>
        </div>
    </div>
</form>
```

is easy! :D

##TODO:
* Parse to Angular 2

###Licence:
Open source
 * @license MIT License, http://www.opensource.org/licenses/MIT