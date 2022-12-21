import React from "react";
import { render, screen } from "@testing-library/react";
import App from "../App";

describe("Search", () => {
  it("renders Search component", async () => {
    render(<App />);
    // expect(screen.queryByText(/Searches for JavaScript/)).toBeNull();
    expect(screen.queryByText(/Logged in as/)).toBeNull();
    screen.debug();
    expect(await screen.findByText(/Logged in as/)).toBeInTheDocument();
    screen.debug();

    // Assertive Functions Examples:
    expect(screen.getByAltText(/search image/)).toHaveClass("image");
    expect(screen.getByLabelText(/search/i)).not.toBeRequired();
    expect(screen.getByLabelText(/search/i)).toBeEmpty();
    expect(screen.getByLabelText(/search/i)).toHaveAttribute("id");
  });
});