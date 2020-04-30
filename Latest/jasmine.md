# [Injection Example](https://codecraft.tv/courses/angular/unit-testing/dependency-injection/);

. TtypescriptTestBed.overrideComponent(
    LoginComponent,
    {set: {providers: [{provide: AuthService, useClass: MockAuthService}]}}
);
. typescriptcomponentService = fixture.debugElement.injector.get(AuthService);
. inject([AuthService], (injectService: AuthService) => {
            expect(injectService).toBe(testBedService);
        })
        
  . inject(
  [token1, token2, token2],
  (dep1, dep2, dep3) => { }
)

# Button Click – SPEC HAS NO EXPECTATIONS

```
<button class="email-edit-button" mat-icon-button (click)="editSharedFormControl('emailAddress')">
    <mat-icon>edit</mat-icon>
</button>

```
. Frist way

```
it('click emailAddress Edit button should allow form control enabled', ()=> {

fixture.whenStable().then(() => {
  let button = fixture.debugElement.query(By.css('.email-edit-button')).nativeElement;
  button.click();
  tick();
  fixture.detectChanges();
  expect(component.editSharedForm.get('emailAddress').enabled).toBe(true);
  });
});

```
. Second way

```
it('click emailAddress Edit button should allow form control enabled', async (()  => {

fixture.whenStable().then(() => {
  let button = fixture.debugElement.query(By.css('.email-edit-button')).nativeElement;
  button.click();
  tick();
  fixture.detectChanges();
  expect(component.editSharedForm.get('emailAddress').enabled).toBe(true);
  }); 
}));

```
