# SimpleEmployeeProject
public ActionResult NewEmployee()
        {
            List<SelectListItem> _Country = new List<SelectListItem>();
            using (EmployeeEntities db = new EmployeeEntities())
            {
                var Countries = db.Countries.ToList();
                foreach (var i in Countries)
                {
                    _Country.Add(new SelectListItem { Text = i.CountryName, Value = i.CountryId.ToString() });
                }
            }
            ViewBag.CountryList = _Country;
            return View();
        }
  
  
  
  
  
  
  
  
  
@model SimpleEmployee.Models.Employee


<form method="post">

    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.FirstName)
        </div>
        <div style="display:inline-block">
            @Html.EditorFor(x => x.FirstName)
        </div>
    </div>
    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.LastName)
        </div>
        <div style="display:inline-block">
            @Html.EditorFor(x => x.LastName)
        </div>
    </div>
    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.Gender)
        </div>
        <div style="display:inline-block">
            @Html.EditorFor(x => x.Gender)
        </div>
    </div>
    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.BirthDate)
        </div>
        <div style="display:inline-block">
            @Html.EditorFor(x => x.BirthDate)
        </div>
    </div>
    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.City)
        </div>
        <div style="display:inline-block">
            @Html.EditorFor(x => x.FkCity)
        </div>
    </div>
    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.State)
        </div>
        <div style="display:inline-block">
            @Html.EditorFor(x => x.FkState)
        </div>
    </div>
    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.Country)
        </div>
        <div style="display:inline-block">
            @Html.DropDownListFor(x => x.FkCountry, (IEnumerable<SelectListItem>)ViewBag.CountryList)
        </div>
    </div>
    <div>
        <div style="display:inline-block">
            @Html.LabelFor(x => x.Department)
        </div>
        <div style="display:inline-block">
            @Html.EditorFor(x => x.FkDepartmentID)
        </div>
    </div>
    <div>
        <button type="submit">Submit</button>
    </div>
</form>


