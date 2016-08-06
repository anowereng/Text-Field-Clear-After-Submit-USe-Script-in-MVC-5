<script>
    $(document).ready(function() {
        $('form input:text').val('');
    });

</script>
------------------------------------------------------------
@using (Html.BeginForm("StudentAdd","Student",FormMethod.Post,new{id="studentForm"})) 
{
    @Html.AntiForgeryToken()
    
    <div class="form-horizontal">
        <h4>Student</h4>
        <hr />
        @Html.ValidationSummary(true)

        <div class="form-group">
            @Html.LabelFor(model => model.Name, new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Name)
                @Html.ValidationMessageFor(model => model.Name)
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Email, new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Email)
                @Html.ValidationMessageFor(model => model.Email)
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.ContactNo, new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.ContactNo)
                @Html.ValidationMessageFor(model => model.ContactNo)
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Date, new { @class = "control-label col-md-2 "})
            <div class="col-md-10">
                @Html.EditorFor(model => model.Date,new{ @class="form-control"})
                @Html.ValidationMessageFor(model => model.Date)
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Address, new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Address)
                @Html.ValidationMessageFor(model => model.Address)
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.DepartmentId, new {@class = "control-label col-md-2"})
            <div class="col-md-10">
                @Html.DropDownList("DepartmentId", new SelectList(ViewBag.getDepartment, "Value", "Text"))
                @Html.ValidationMessageFor(model => model.DepartmentId)
            </div>
        </div>
        @*<button type="reset" value="Reset" class="btn-cancel" onclick="resetMulti();">Reset</button>*@

        <div class="form-group">
            <div class="col-md-offset-2 col-md-10">
                <input type="submit" value="Create" class="btn btn-default" id="submit" />
            </div>
        </div>
    </div>
}
